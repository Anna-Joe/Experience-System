## PSASP模型拼接说明

### 待解析的卡

ST.NS4 LF.AREA LF.ZONE

### 待参与拼接的卡

LF.AREA LF.ZONE

### 参与拼接的卡

- 稳态卡

LF.PStation 厂站

LF.L7 分区

LF.L10 分区打折卡

LF.L1 母线

PHYBUS.LFI 母线编号

LF.BUS 母线厂站

LF.L20 预设平衡点

LF.L6 负荷

LF.L5 电源

LF.L2 交流线路

LF.L3 绕组

- 暂态卡

ST.S1 暂态/母线编号

ST.S6 暂态/负荷

ST.S5 暂态/发电机

ST.S2 暂态/交流线路

ST.S3 暂态/绕组



### 直接保留外网文件的卡

LF.L0算例

LF.L4 直流线路

LF.NL4

LF.ML4 VSC#s

ST.S4 暂态/直流线路

ST.S7 暂态/静止无功补偿器

ST.SCC 短路/功能设置

ST.SCDATE 短路/条件设置

ST.NS4

ST.MS4

ST.MLCC

DATALIB



### 待刷新母线编号的卡

ST.NS4

### 刷新母线编号的卡

PHYBUS.LFI 母线编号

LF.BUS 母线厂站

LF.L20 预设平衡点

LF.L6 负荷

LF.L5 电源

LF.L2 交流线路

LF.L3 绕组

LF.L4 直流线路

LF.NL4

LF.ML4 VSC#s



ST.S1 暂态/母线编号

ST.S6 暂态/负荷

ST.S5 暂态/发电机

ST.S2 暂态/交流线路

ST.S3 暂态/绕组

ST.S4 暂态/直流线路

ST.S7 暂态/静止无功补偿器

ST.MS4

ST.MLCC