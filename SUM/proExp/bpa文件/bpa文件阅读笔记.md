## bpa文件阅读笔记

![](D:\tasks\task5bpa文件\bpa读写过程.png)



### .dat文件适配ZSystem

| 与BPA_memDb的接口（从哪个表读到）         | 卡名称                                                       | 用途                                                         | ZSystm映射                                                   |
| ----------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| bpaBDTable.records()                      | **B卡** 交流节点数据                                         | 适配ZSystm的节点                                             | ZSystem::addBusBar()                                         |
| namedTable("bpa+")                        | **+卡** 延续节点数据                                         | 添加负荷                                                     | ZSystem::addGroundBranch()                                   |
| namedTable("bpaBZ")、namedTable("bpaBZ+") | **BZ卡** 柔性直流节点数据卡、**LZ卡** 柔性直流线路数据卡     | 添加电源换流器 节点信息和线路信息                            | ZSystem::addBranch()                                         |
| namedTable("acline_param")                | **L卡** 对称线路数据卡、**E卡** 不对称线路数据卡             | 添加线路                                                     | ZSystem::addShunt()、ZSystem::addBranch()、ZSystem::addSwitch() |
| namedTable("bpaR")、namedTable("bpaT")    | **T卡** 变压器和移相器数据卡、**R卡** 带负荷调压变压器和移相器控制卡、**P卡** 未知 | 添加变压器                                                   | ZSystem::addBranch()                                         |
| namedTable("bpaLD")                       | **LD卡** 两端支流线路数据卡                                  | 添加指定线路                                                 | ZSystem::addBranch()                                         |
| namedTable("bpaX")                        | **X卡** 可切换电抗/电容器卡                                  | 添加指定电容器组、电抗器组                                   | ZSystem::addCap()                                            |
| namedTable("bpaP")                        | **P卡** 未知                                                 | 添加分区信息 感觉是把分区信息加入已有的发电机、负荷里面去，然后构造一个分区映射 | ZSystem::Generator()、ZSystem::Load()、ZSystem::ZoneMap()    |



### .swi文件适配ZSystem

| 与BPA_memDb的接口（从哪个表读到）                            | 卡名称                          | 用途                       | ZSystm映射                                                   |
| ------------------------------------------------------------ | ------------------------------- | -------------------------- | ------------------------------------------------------------ |
| namedTable("swiXO")                                          | **XO卡** 变压器零序模型         | 添加零序电抗电阻的信息     |                                                              |
| namedTable("swiMC")、
namedTable("swiMF")、
namedTable("swiMG") | **MC卡、MF卡、MG卡** 发电机模型 | 给发电机节点添加暂态信息   | node-><br />addTransientRecord(subId,transientRecord);       |
| namedTable("swiM")                                           | **M卡** 发电机次暂态参数模型    | 给发电机节点添加次暂态信息 | node-><br />addSubtransientRecord(subId,subtransientRecord); |
| namedTable("swiE")、namedTable("swiF")                       | **E卡、F卡** 励磁系统模型       | 给发电机节点添加暂态信息   | node-><br />addTransientRecord(subId, transientRecord)       |
| namedTable("zjuGN")                                          | **MZ卡** 浙大华东扩展           | 序阻抗信息                 | node-><br />setSequenceParameterRecord<br />(sequenceParameterRecord); |
| namedTable("zjuGB")                                          | **zjuGB卡** 对地支路零序参数卡  | 序阻抗信息                 | node-><br />addLoad(eRecord);                                |

