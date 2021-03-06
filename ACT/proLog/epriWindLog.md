# 工作进展

## 2020.0814

### SVG参数辨识-增加适应度显示

#### 需求

3.1 针对 PSO 优化过程，需提示“设定值”对应的适应度，需在优化结束后提示“优化后”的适应度，便于使用者比较并决定是否重新优化。）

3.1 粒子群优化（PSO）在最开始时先针对“设定值”列的数据计算适应度（fitness）并显示，在耗时的优化结束后显示找到的最优解的适应度，由人工比较这两个数值并决定是否再优化一次。（考虑显示在界面上）

#### 实现

在计算的过程中记录 初始的全局适应度 和 优化之后的全局适应度



## 2020.0817

### 添加LS阻抗参数搜索功能

#### 需求

2.1计算工况前应通过调用 BPA 程序算得故障的接地阻抗，不再使用设置文件 WindfarmFaultParams.csv。

2.1 目前使用已经固化在配置文件里的参数在计算时修改 LS 卡，但对于不同的风电场模型显然有不同的参数，不能期待使用者先调好了在这里直接用。需要在计算前要求先找出所需的故障接地阻抗参数（加个按钮），在计算前先检查所需的参数已准备完毕（防止临时修改了工况），后续就可以去掉一个配置文件，再加上可加载/保存已算好的参数、可增量计算部分参数的功能。之前考虑了可以用二分查找。

确定R和X的规律

计算之前用算法确定 给定残压下 的R和X

#### 实现

- 点击界面上组合按钮会触发RX参数的搜索过程

- 输入未计算过的故障类型和残压幅值会触发计算过程

- 已计算过的，会直接返回搜索结果

- 搜索过程会保存 计算过程和搜索结果 为配置文件cfg/windfarmFaultParams.etext

- 搜索完成 在界面上显示搜索结果

- 搜索过程：

  - 从R=0,X=0开始遍历，根据不同故障类型设定每次增加的步长
  - 如果初始的残压已经大于目标残压 则返回R=0,X=0
  - 当 遍历的残压值大于目标残压时，会调小X值，X缩小的步长也时根据故障类型设定的



## 2020.0818

### 修改等值建模计算过程

#### 需求

4.1修改界面和交互。 操作流程修改为：生成/加载等值模型 → 零序参数优化 → 计算 → 生成报告。
4.2 参数优化时，针对每一条等值线路分别寻优，将故障设置在等值线路“主变低xx”母线侧。（注意修改图表显示。）
4.2 目前故障在靠近电源的位置（如"海上升压"），但实际应放在"主变低xx"。则在有多个"主变低xx"时需分别设置故障并通过优化过程找到各自所带的简化接线部分的零序参数。



## 2020.0922

### 修改包含搜索阻抗参数在内的计算逻辑

- 1.将故障侧修改为仅在等值模型中设为“主变低”
- 2.参数搜索过程内化到所有计算之前
  - 因等值建模部分参数搜索涉及到了两种模型（等值和详细），因此给参数搜索的结果文档添加“模型”字段，由此改动了所用涉及到结果文档的判断代码
- 3.计算过程曲线均保存为图片

### 界面及输出的相关修改

- 1.修改生成报告
- 2.修改主窗口界面布局





## 2020.1016

### 需求

- 1.界面修改 
  - 加载文件模型过程修改到每个子功能启动时
  - 子功能启动时， 可同步显示拓扑结构，且不可启动其他功能
- 2.ls阻抗参数搜索算法修改 
  - 在 [-5.5, 0.0) 内二分取 x，令 R=X=e^x，则 R, X∈[0.004, 1.0)，仿真结果的 curVolt 与 remVolt 比较并决定是否断续二分
- 3.结果报告中，类似P=0.86Pn 小数只保留两位小数



## 2020.1017

### 需求

- 1.ls阻抗参数搜索过程修改
  - 只搜索详细模型
  - 搜索结束询问是否继续计算
- 2.报告 第四章标题不使用代码生成
- 3.曲线颜色修改



## 2020.1028

发现swnt调用路径中含有“-”会影响计算



## 2020.1105

### 需求

1. 寻找 LS 卡阻抗参数的过程均使用详细模型，所得结果数据同时用于详细/等值模型。因此 windfarmFaultParams.etext 中不需保留与等值有关的内容，弹窗提示与使用时不再区分详细/等值。√
2. 舟山风场的“主变低01”和“主变低02”所接的风机规模不同，找到的 R, X 值却相等。代码是否有误？√
3. 残压为 0.72 时仿真输出曲线的残压值为 0.66，需检查是否是故障起止时刻附近的数值抖动造成了取平均值时的偏差。√
4. 每次启动零序参数优化过程时，应只对一组 R, X, B 进行搜索。√
5. 需手工测试郭老师生成等值模型时给出的 LO 卡零序阻抗参数是否已接近正确值（即比较两者仿真结果中的无功曲线的差异），然后考虑是否删去 optimization.ini 中的 [Bounds] 段（改为自动确定上下限）。
6. “等值建模”的“计算”结束后保存的曲线图片不完整，是否是因重名而覆盖了前面一组的文件？dui
7. 界面中的“持续时间”文本框是否有必要保留，待与电科院讨论。
8. “低穿验证”在生成报告时窗口大小的变化可感知，且生成结束后未恢复。√
9. “低穿验证”的“计算”结束后保存的曲线图片似也存在覆盖的情况。√
10. “低穿验证”所生成报告的附录有部分数据需修改。√

### 实现

- 生成报告（6、7、8、9、10）
  - 修正文字，数据上的问题
  - 修正生成图片保存问题
  - 修正低穿验证窗口问题
- 参数搜索(1、2)
  - 不再区分详细和等值
  - 主变不同 RX相同是因为 两个主变残压下降的趋势接近（有差异但是差异很小）
- 零序参数优化（4）
  - 修改每次计算参数的数量为3
- 计算 曲线残压问题（3）
  - 我这测试的曲线一直是震荡的 残压也没降到设定值 没搞清楚咋回事
  - 起始时刻的震荡没有计算在参数搜索的过程中



## 2020.1113

### 需求

- 对于等值建模模块中的以下过程：
  (A1)确定“主变低xx”LS 卡的阻抗参数值 → (A2) 通过“主变低xx”处的故障进行零序参数寻优 → (A3) 确定等值模型的全部参数。
  (B1)确定“陆上计量”LS 卡的阻抗参数值 → (B2) 通过“陆上计量”处的故障进行计算 → (B3) 获得报告所需的曲线。
  - 1.1. 对于 220kV 电压等级，故障阻抗参数按 R:X = 1:8 确定各残压下的数值。√
  - 1.2. A1 仍使用固定的工况，通过二分查找需写入的故障阻抗值，但应注意对特殊情况（无法降到所需残压值等）的处理，避免计算次数过多。
  - 1.3. 针对计算结果的残压值与窗口指定的残压值不一致的情况，应修改代码中的错误：故障阻抗寻参时应考虑系统短路阻抗并修改电源接出线路的电抗值。√
  - 1.4. 保留 B1 的中间文件。√

- 等值建模报告

  - 2.1. 第 4 章首段中短路阻抗的计算：大/小方式下分别用电源接出线路的阻抗值得出极坐标形式。

  - 2.2. 检查在不同分辨率下存入报告的图片是否保持排版一致。√

    

- 界面

  - 4.1. 等值建模窗口中去掉“零序参数优化”按钮，在生成模型后即开始寻优，并在界面显示进度条。√
  - 4.2. 考虑使用第三方图形库，用于处理曲线图的界面显示和保存文件、写入报告。
  - 4.3. 拓扑图默认填充窗口。



### 实现

- 报告
  - √ 曲线图片大小固定使用7.4厘米（2.2 4.2）
  - √ 增加通过阻抗值计算极坐标值的函数以处理等值建模报告第四章（2.1）处理方法见下图
- 界面
  - √ 修复拓扑图显示不正常的问题（4.3） 拓扑图形在打开窗口的时候 使用固定的比例放大了
- LS参数搜索
  - √ 修改R = X/8.0（1.1）
  - √ 检查是否有搜索次数过多无法结束的情况（1.2）检查 单相+0.72当前算法是有穷计算并且有参数结果
- LO参数搜索
  - √ “零序参数优化”按钮中的内容合并到“生成模型”，并添加进度条展示模型生成过程（4.1）



## 2020.1127

### 需求

1. 光伏电站的等值建模

- 1.1. 风电、光伏在 swi 文件中的机组模型所用卡片不同，需分别适配和操作。
  适配等值的过程（统计数量）
- 1.2. 针对光伏电站的模型测试整个程序。√



2. 等值建模报告

- 2.1. 系统短路阻抗的计算：确定大/小方式下系统零序短路阻抗的计算方法。
  - 记详细模型中电源接出线的 R / R0 = k_R, X / X0 = k_X，又有算得的等值模型电源接出线的 R', X'，则
    等值模型电源接出线的 R0' = R / k_R, X0' = X / k_X，进而可算得 Z'∠θ, Z0'∠θ'。
- 2.2. 报告的整体检查。



4. 界面

- 4.1. 测试 ECharts 在“等值建模”、“低穿验证”界面应用的效果。

- 4.2. 第二次打开拓扑图时应仍使整个图填充窗口，而非以 1:1 显示。



3. 测试

- 3.1. 检查郭老师生成的简化模型中的等值线路零序参数在各种工况下的适用性，检查粒子群优化得出的等值线路零序参数在各种工况下的适用性。

- 3.2. 检查在哪些工况下的哪些曲线在调用 swnt-V5.4.6-20191026.exe 后输出的 U/I/P/Q 曲线出现振荡。

### 实现

- 光伏电站的测试（修改数据文件中的节点名称 启备变低》》》主变低01）【对应需求1】
  - 短路容量修改为 光伏电站的总容量
  - 短路比 大于4 的潮流计算不收敛
  - 三相短路 残压0.37可以计算（最高好像到不了0.72）
  - 两相接地 残压0.72可以计算（最低到不到0.37）
  - 两相相间 同上
  - 单相接地 算不了（最高是0）
- 修复界面上的几个bug
  - 显示搜索LS参数报错的时候，报错的内容显示有误
  - 低穿验证的图形不能正常显示(存放图形数据的map key已经修改)
  - 拓扑图形的显示及放大不正常的问题【对应 需求4.2】
- 等值建模 和 低穿验证 图形修改为Echarts【对应 需求4.1】
- 等值建模报告中的阻抗描述内容已修改【对应 需求2】
- 零序参数优化 优化曲线数据源修改【对应 临时增加的需求】
  - 详细模型中的“无功功率”取自所有与“主变低”相连的线路

