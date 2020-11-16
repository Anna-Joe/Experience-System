# avc修改日志

## LOG 9-16

### avc_report

#### **添加母线电压范围设置 和 功率范围设置**

- 配置文件（avc_report_config）
  - $$(BUS_VOLTAGE_RANGE:1,15:10母线电压范围:)
  - $$(POWER_RANGE:295,333:300功率范围:)

- 代码修改 (avc_reportdialog.h avc_reportdialog.cpp)
  - AVC_ReportDialog::init 仅修改
  - AVC_ReportDialog::initMacroMap 仅修改
  - AVC_ReportDialog::updateGroupBox 新增
  - AVC_ReportDialog::spinBoxValueChanged 新增
- 测试方法
  - 在配置文件中SQL语句插入上述范围宏定义，可在界面上显示范围的设定框
  - 设定结束后点刷新按钮刷新筛选的范围记录



### avc_interface

#### **添加线路潮流表的写入**

- 代码修改 (avc_cmdfilesaver_open3000.h avc_cmdfilesaver_open3000.cpp)
  - AVC_CmdFileSaver_OPEN3000::saveCmdFileToHisdb 仅修改
  - AVC_CmdFileSaver_OPEN3000::saveLinePfInfoToHisdb 新增
- 测试方法
  - 看新增的线路表有没有写入



#### 修改负荷采样表的域值和表值为从配置文件读取

- 配置文件（avc_defaultparam）
  - 添加表avc_default_load_param
  - 第一个域 对应负荷采样表的域名 第二个域对应 表名
- 代码修改 (avc_snapshotsaver_open3000.cpp)
  - AVC_SnapshotSaver_OPEN3000::initLoadToRtdb 仅修改
  - AVC_SnapshotSaver_OPEN3000::initLoadToReldb 仅修改
- 测试方法
  - 能否成功获取采样表的负荷值



## LOG 9-17

### avc_command

#### 母线控制参数遥测名从表中读取

- 代码修改（dboperater.h dboperater.cpp avccmdtestdlg.h  avccmdtestdlg.cpp)
  - AVC_CmdTest::showNewEnergyVolInfo 仅修改
  - DBOperator::getNewEnergyBusbarYcInfo 仅修改
  - AVC_CmdTest::showPlantVolInfo 仅修改
  - DBOperator::getBusbarYcInfo 仅修改
  - DBOperator::getControlParamsByStid 新增
- 测试方法
  - 在command_test界面上选择母线 看是否能返回正确的遥测信息

