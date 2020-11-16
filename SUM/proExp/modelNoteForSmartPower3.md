## 功能模块笔记

[TOC]

注意1 我在搜索函数的时候习惯使用.h文件做入口，.h文件的函数目录起到一个类似索引的作用。

注意2 代码追踪的顺序都是自顶向下的。

-----

### 20190530 网络拓补查看器

- 功能使用：

  - 【智能计算3.0】新建》文件模型》（打开任意一个BPA文件）》测试》网络拓补

  - 可以查看发电机 线路 变压器 开关这四种电网数据的拓补结构

- 代码位置：

  - ../../src_intel/newsmartpowercli

  - ztopologywindow.ui
  - ztopologywindow.h
  - ztopologywindow.cpp

- 代码追踪：

  - mainwindow.h

    - #include "ztopologywindow.h"
    - ZTopologyWindow m_ztopologywindow;
    - void showNetTopology();

  - mainwindow.cpp

    - void MainWindow::initTestCode()
      - addTestAction(QStringLiteral("网络拓补"),QStringLiteral("showNetTopology"));
    - void MainWindow::showNetTopology()
      - m_ztopologywindow.loadSystem(m_engine.system());
      - m_ztopologywindow.show();

  - ztopologywindow.h

    - 继承了QMainWindow
    - 初始化了整个“查看拓补类”的一些函数

  - ztopologywindow.cpp

    - ZTopologyWindow::ZTopologyWindow(QWidget *parent, Qt::WFlags flags): QMainWindow(parent, flags)

      构造函数 主要是加载界面组件，并且建立两个信号槽。一个是更新列表的信号槽函数，一个是更新拓补树的槽函数。

    - void ZTopologyWindow::loadSystem(ZSystem &S)

      负责把程序中获取的system类交给ztopologywindow类。

    - void ZTopologyWindow::updateList(int selected)

      更新列表（槽函数）

    - void ZTopologyWindow::loadXXX()

      凡以load开头的函数都是为了加载列表中的值（各个设备的rdfid）

    - void ZTopologyWindow::updateTree(QListWidgetItem* li)

      更新拓补树（槽函数）

    - void ZTopologyWindow::searchXXX(ZString d_rdfid)

      凡以search开头的函数都是为了加载拓补树的值（各个设备首末端的rdfid以及该节点上所有的设备）



### 20190617 bpa工具-修改设备名称（bpa名称刷新）

- 功能使用：

  - 【智能计算3.0】bpa工具》修改设备名称

  - 主要是使用参数库中的数据刷新.dat文件（一般是省调文件，即外网文件）中不一致/空白/重复的线路名和主变名

- 代码位置：

  - ../../src_intel/lib_bpa_tool

  - zbparenamedialog.ui
  - zbparenamedialog.h
  - zbparenamedialog.cpp

- 代码追踪：

  - newsmartpowercli/mainwindow.h

    - `void bpaToolTranName();                 //bpa工具，修改设备名称`

  - newsmartpowercli/mainwindow.cpp

    - void MainWindow::initBpaCode()
      - `addBpaAction(QStringLiteral("修改设备名称"), QStringLiteral("bpaToolTranName"));`
    - void MainWindow::bpaToolTranName()
      - `ZBpaRenameDialog dialog(m_dbc, this);dialog.exec();`

  - lib_bpa_tool/zbparenamedialog.h

    - 枚举类存储"重命名规则"
      - Rule_NULL = 0x00
      - Rule_Topo = 0x01,   //按照拓扑，首末端母线匹配。重复的按照编号来匹配
      - Rule_Code = 0x02,   //使用编号来匹配：对应主变是厂站名+主变编号 线路是四位编号。
      - Rule_Auto = 0x04    //利用首末端节点和回路号自动命名

  - lib_bpa_tool/zbparenamedialog.cpp

    - void ZBpaRenameDialog::on_pushButton_bpaold_clicked()

      打开旧（未命名）的bpa文件

    - void ZBpaRenameDialog::on_pushButton_bpanew_clicked()

      保存新（刷新过）的bpa文件

    - void ZBpaRenameDialog::on_pushButton_start_clicked()

      开始刷新名称按钮 主要是调用rename函数

    - void ZBpaRenameDialog::rename()//因参数列表太长，已省略

      - 线路刷新

        - 从参数库数据里面读取线路拓补信息，生成线路拓补映射。

        - 读取未命名的bpa文件，将文件中的线路信息分为 名称为空或重复的线路和名称唯一的线路这两个列表。

        - 调用renameLine函数分别对两个列表进行名称刷新。

      - 主变刷新

        - 从参数库数据里面读取变压器拓补信息，生成变压器拓补映射。

        - 读取未命名的bpa文件，将文件中的线路信息分为 名称为空或重复的主变和名称唯一的主变这两个列表。

        - 调用renameTran函数分别对两个列表进行名称刷新。

    - void ZBpaRenameDialog::renameLine()//因参数列表太长，已省略

      - 根据从rename函数里面传过来的“重命名规则参数”将分三种情况对线路进行重命名。（重命名就是把L卡“描述”字段修改为线路的bpaID）
      - 1 根据拓补匹配
        - 拓补中不存在该线路（忽略
        - 拓补中仅一条线路（唯一匹配
        - 拓补中多条线路（根据参数库的回路号匹配
      - 2 根据参数库的四位编码匹配
      - 3 使用首末端节点和回路号 自动重命名

    - void ZBpaRenameDialog::renameTran()//因参数列表太长，已省略

      - 1 根据拓补匹配
        - 拓补中不存在该主变（忽略
        - 拓补中仅一个主变（唯一匹配
        - 拓补中多个主变（根据参数库的回路号匹配
      - 2 根据参数库的四位编码匹配
      - 3 使用首末端节点和回路号 自动重命名



### 20190625 bpa工具-模型拼接

- 功能使用：

  - 【智能计算3.0】bpa工具》模型拼接
  - 主要是使用内网bpa信息刷新外网bpa信息。将外网bpa中的相关联的内网信息删除，并将内网bpa信息拼接到外网bpa末尾。

- 代码位置：

  - ../../src_intel/lib_bpa_tool

  （两个工具类和一个窗口类）

  - zbpamerger.h
  - zbpamerger.cpp
  - zbpasplitter.h
  - zbpasplitter.cpp
  - zbpamergedialog.h
  - zbpamergedialog.cpp

- 代码追踪：

  - mainwindow.h

    - `void initBpaCode();`

    - `void bpaToolMerge();                    //bpa工具，模型拼接`

  - mainwindow.cpp

    - void MainWindow::initBpaCode()
      - `addBpaAction(QStringLiteral("模型拼接"), QStringLiteral("bpaToolMerge"));`
    - void MainWindow::bpaToolMerge()
      - `ZBpaMergeDialog dialog(m_dbc, 0, this);dialog.exec();`

  - zbpamergedialog.h

    - 枚举类型 存储“模型拼接的模式”
      - M_NodePrefix,        //节点前缀
      - M_TieLine,           //联络线模式
      - M_Owner,              //所有者
      - M_Zone,              //分区
      - M_NodePrefixAndLowestVolt //节点前缀加最低电压等级

  - zbpamergedialog.cpp

    - void ZBpaMergeDialog::openBpa1()

      - 打开内网文件

      - 根据使用的拼接模式（例如内外网节点染色法）进入对应的获取节点信息函数

        - void ZBpaMergeDialog::mergeByNode( QStringList &rdfIds )

          - QStringList  ZBpaMergeDialog::getPrefixList(const ZEDocument& eDoc)//从document获取节点信息列表
          - QStringList  ZBpaMergeDialog::getGuangdongAreaList(const ZEDocument& eDoc)//对广东数据以分区拼接模型做了特殊处理

          - 在前端展示节点信息列表的同时 获取了被选中的节点列表

            //不知道具体的原理但是感觉这个获取被选中节点列表的代码很神奇

    - void ZBpaMergeDialog::openBpa2()

      - 打开外网文件

    - void ZBpaMergeDialog::doMerge()

      - 实现拼接功能的主要函数
      - 根据使用的拼接模式（例如内外网节点染色法）进入对应的子拼接函数
      - bool ZBpaMergeDialog::mergeBpaByNode(const QString& mergeSavePath)
        - 按分区拼接
          - bpaMerger.mergeByArea
        - 按前缀拼接
          - bpaMerger.mergeByPrefix

  - zbpamerger.cpp

    - 按分区拼接 bool  ZBpaMerger::mergeByArea()//参数列表太长已省略

      - 1 splitter.splitInternalByArea

        需要先处理内网文件，对于内网文件进行一次删减

      - 2 splitter.splitExternalByArea

        再根据获取的内网信息，对外网文件进行一次删减

      - 上述两个函数最终都会定位到 bool ZBpaSplitter::splitByArea（）

      - 3 把内网信息拼接再外网文件末尾

    - 按前缀拼接 同理

  - zbpasplitter.cpp

    - bool ZBpaSplitter::splitByArea（）
      - 根据bpa信息中的不同卡类型分割节点
      - B卡信息 void ZBpaSplitter::splitBpaNodeByArea
        - 将符合条件的分区信息记录在列表里以便L卡T卡信息的筛选
        - 符合筛选条件的作为“内网信息” 不符合的作为“外网信息”
        - “内网信息”保留 “外网信息”删除
      - L卡T卡信息 ZBpaSplitter::splitBpaBranchByArea
        - 利用从上述函数里得到的分区节点信息筛选支路
        - 原理同上述

    

### 20190702 浏览参数库

- 功能使用：

  - 【智能计算3.0】浏览参数库》BPA导出
  - 根据参数库的数据导出BPA文件

- 代码位置：

  - ../../src_intel/lib_smart_ui

    - newdbc_managerdialog.h

    - newdbc_managerdialog.cpp

  - ../../src_intel/lib_bizmemdb

    - zdbsnapshot.h
    - zdbsnapshot.cpp

- 代码追踪：

  - mainwindow.h

    - void showDbc();

  - mainwindow.cpp

    - void MainWindow::showDbc()
      {
          ZSqlQuery query;
          NewDbc_ManagerDialog dlg(query,true,m_dbc);
          dlg.exec();
      }

  - newdbc_managerdialog.h

    - void on_pushButton_export_bpa_clicked();

  - newdbc_managerdialog.cpp

    - void NewDbc_ManagerDialog::on_pushButton_export_bpa_clicked()

      - m_dbSnapshot->buildBpaFile(memDb, errList, infoList, false)；首先建立bpa内部缓存

      - memDb.saveAsBpa(toZString(fileName));通过memdb读取内部缓存 并保存为bpa文件

  - zdbsnapshot.cpp

    - void ZDbSnapShot::buildBpaFile（）
      - 首先区分电气岛（电气岛是电网拓补结构中相互连接的节点）就是判断母线和主变是否在电气岛之中
      - 之后遍历电气岛中所有的节点 通过参数库的信息建立dat文件的电气岛
      - （东莞数据导出bpa部分信息丢失的原因就是：原先该代码的逻辑是每个电气岛建立一个新的bpa文件表，广东数据只有一个电气岛，所以导出的bpa文件无误。但是东莞数据含有三个电气岛，新的bpa文件表会覆盖上一个电气岛的信息，所以需要修改代码逻辑。将所有电气岛节点信息放进一个映射中去）
    - void ZDbSnapShot::buildDatIsland()
      - 通过这个函数建立新的bpa表
    - 上述函数调用完成后bpa数据储存在bpaDocument中



### 20190710 BPA引擎潮流计算

- 功能使用：

  - 【智能计算3.0】新建》文件模型》打开.dat文件（同目录下需要有.swi文件，在打开的时候会一并搜索，加载）
  - 对潮流计算引擎配置
    - 双击潮流计算》计算引擎选中BPA》计算程序选中pfnt.exe
  - 对短路电流计算引擎配置
    - 双击短路电流扫描》计算引擎选中BPA》计算程序选中SCCPC.exe
  - 使用智能计算系统做bpa潮流计算

- 代码位置：

  - ../../src_intel/newsmartpowercli 集中界面上的交互

    - zchecksequencewidget.ui
    - zchecksequencewidget.h
    - zchecksequencewidget.cpp
    - zsequencecotrolwidget.ui
    - zsequencecotrolwidget.h
    - zsequencecotrolwidget.cpp

    - mainwindow.h
    - mainwindow.cpp

  - ../../src_intel/lib_smart_ui 智能计算客户端跟计算程序的交互

    - znewcalmanager.h
    - znewcalmanager.cpp

    - znewsmartabstractclient.h
    - znewsmartabstractclient.cpp
    - znewsmartabstractserver.h
    - znewsmartabstractserver.cpp
    - znewsmartclientserver.h
    - znewsmartclientserver.cpp

- 代码追踪：

  - znewcalmanager.cpp
    - ZNewCalManager ZNewCalManager::s_sinleton 在mainwindow加载之前先创建这个单例
    - 创建两个ZNewSmartClient对象，和一个ZNewSmartServerStarter对象
  - main.cpp
    - main函数里面调用ZNewCalManager的单例并执行start()函数
  - znewcalmanager.cpp
    - ZNewCalManager::start()
      - int localPort = m_localServer.startSvr(true);
  - znewsmartclientserver.cpp
    - ZNewSmartServerStarter::startSvr()
      - start()
      - 对于QThread（ZNewSmartServerStarter继承了QThread）而言，start()一旦执行就会激活run()函数
      - 在run()函数中创建服务

  - mainwindow.cpp

    - void MainWindow::calSnapshotByPoint()
      - 主要是从界面上获取runCalculate所需要的两个参数，被选中的计算方式

    - void MainWindow::runCalculate(int row, int column)
      - 获取计算方式（以BPA为例）
      - 从m_engine里面读取文件模型里获取到的bpa数据信息，猜想这里可能是利用参数库更新了一下memdb，生成计算用的bpa文件
      - 自定义局部变量engine读取计算用的bpa文件，并且生成计算用的e文件集。
        - ZNewCalDocumentSet::prepareDocSet
          - `s->m_inputDocSet->addDocument(NewCalSetting::s_fileDbCache, dbCacheDoc);//生成数据库E文件`
          - `setting->m_inputDocSet->addDocument(NewCalSetting_TransLimit::s_fileTransLimitSnapshot, snapDoc);//生成热稳断面E文件`
          - 调用QString ZNewCalDocumentSet::prepareFileDoc
            - `setting->m_inputDocSet->addDocument(NewCalSetting::s_fileBpaNet, new ZEDocument(engine.bpaDb().bpaDocument()));//生成BPA模型E文件`
            - `setting->m_inputDocSet->addDocument(NewCalSetting::s_fileBpaConfig, configDoc);//生成BPA配置E文件`
        - 标记哪列被计算

  - znewsmartclientserver.cpp

    - void ZNewSmartServerHandler::onBytesArrived()
      - client传来的数据，server通过这个函数接收并转码
        - ZSmartNetUtil::decode(readedBuffer, action, argument, setting)
      - 调用onProcess（）进行计算程序的计算
        - m_calServer->onProcess(setting, *(setting->m_inputDocSet));
    - znewsmartabstractserver.cpp
      - QString ZNewSmartAbstractServer::onProcess
        - 通过setting里的计算方式选择对应的算法程序
        - 选择算法程序之后（以BPA 为例）
        - 首先加载BPA文档，然后生成计算程序调用的BPA文件
        - 调用计算程序pfnt.exe
        - 读取数据库文件
        - 解析结果文件



### 20190812 暂态信息输出选择

- 功能使用：

  - 智能计算3.0 》潮流 》暂态故障扫描 》输出选择
  - 单击单选按钮+“选择”键 新建新的坐标变量
  - 双击已有坐标可以查看坐标内部
  - 主要就是读写ST.SME文件

- 代码位置

  - ../../src/src_lib/nas_ui 

    - 数据处理层
      - ztransientexport.h
      - ztransientexport.cpp

    - 界面展示层
      - ztransientexportdialog.ui
      - ztransientgendegdlg.ui
      - ztransientbuspudlg.ui
      - ztransientgendlg.ui
      - ztransientaclinedlg.ui
      - ztransientdclinedlg.ui
      - ztransientbusdegdlg.ui
      - ztransientloaddlg.ui
      - ztransientexportdialog.h
      - ztransientexportdialog.cpp

- 代码追踪

  - mainwindow.cpp
    - MainWindow::modelTransientDef()//暂态故障扫描
    - 进入暂态故障扫描的窗口
  - ztransienttemplatedialog.h
    - void showExportDialog();    // 重庆：显示输出信息选择界面
    - 在这里加载界面 并且更新ST.SME的信息
  - ztransienttemplatedialog.cpp
    - void ZTransientTemplateDialog::on_pushButton_calc_chq_clicked()//计算
  - ztransienttemplatelogic.cpp
    - QString ZTransientTemplateLogic::togglePsaspProcess()
  - ztransientfaultmemdb.cpp
    - QString ZTransientFaultMemDb::generatePsaspSTFiles()
    - //把SME文件复制过来
    - 写了一段复制SME文件到“PSASP准备文件夹”的代码
  - ztransientexport.cpp
    - ZTransientExport类
      - 思路主要是在读取psaspDocument之后 按照已解读的信息分为9个Map和9个List
      - list的下标作为坐标序号，list存储的内容为坐标名称。
      - map的key为坐标序号，map的value为该坐标下的数据。
      - 收集到不同的列表和映射之后，可根据界面上传回的信息读取对应的数据。
      - 已解读的信息：
        - 发电机功角 1 gendeg
        - 母线电压 2 buspu
        - 发电机变量 3 genvar
        - 直流线路 6 dcline
        - 交流线路 7 acline
        - 母线电压相角/频率 12 busdeg
        - 负荷变量 14 load
        - 监视坐标 8 monitor
        - 最后一行 11 last
  - ztransientexportdialog.cpp
    - ZTransientExportDialog
      - 主界面负责调用七个分界面
    - ZTransientGendegDialog
      - 发电机功角界面
      - 所需信息：所有分区，所有发电机，发电机对应的编号
    - ZTransientBuspuDialog
      - 母线电压界面
      - 所需信息：所有分区，所有母线，母线对应的编号
    - ZTransientGenDialog
    - ZTransientDClineDialog
    - ZTransientAClineDialog
    - ZTransientBusdegDialog
    - ZTransientLoadDialog
    - 以上界面所需信息在ZTransientExport类中都有对应的函数可以获取。



### 20190814 网络重构

- 功能使用
  - 智能计算3.0 》工具 》网络重构
  - 加载BPA文件》读取当前BPA文件的供区信息 》选择部分供区 》将供区信息生成ETEXT 》并且生成对应的全接线BPA文件
- 代码位置
  - ../../src/src_intel/newsmartpowercli
    - znetrefactordialog.ui
    - znetrefactordialog.h
    - znetrefactordialog.cpp

- 代码追踪
  - 界面主要是所有供区列表和已选供区列表。
  - znetrefactordialog.cpp
    - initSupply()//初始化供区列表
    - saveDocument()//生成E文档和BPA文档



### 20191012 修改未知厂站名称

ZDbSubstation* ZDBHelper::createSubstationFromZSystem