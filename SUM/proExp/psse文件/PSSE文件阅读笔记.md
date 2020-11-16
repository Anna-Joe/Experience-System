##  PSS/E文件阅读笔记

### 系统中读写PSSE文件的总流程

![](D:\tasks\task7psse文件\PSSE文档的读写总流程.png)

### .raw文件的解析

psse_memdb中的parseRaw函数，分为十八部分数据（算例，母线，负荷，固定补偿器，发电机，非变压器支路，变压器，区域，双端直流输电线路，vsc直流传输线，变压器阻抗校正，多端直流线路，多段线路组，区域间交换，拥有者，FACTS设备，可投切并联补偿器）进行解析。

最根本的数据解析方法（函数readTable实现）是 **顺序从文件中读取行，通过数据长度来分割不同类型的数据（textSource.readLine(m_buffer, sizeof(m_buffer))）**

算例 是处理文件的前三行数据，读取文件的基本信息。

非变压器支路，变压器，双端直流输电线路，vsc直流传输线 根据数据的特殊性做了特殊的数据筛选处理。

其余的十三种数据均直接调用readTable实现。

raw文件的数据可以直接在PSSE32软件中阅读到。



### .seq文件的解析

psse_memdb中的parseSeq函数，分为八部分数据（修改码，发电机正序参数，发电机负序参数，发电机零序参数，负荷负序参数，负荷零序参数，线路零序参数，线路零序互阻抗）进行解析。

最根本的数据解析方法（函数readTable实现）是 **顺序从文件中读取行，通过数据长度来分割不同类型的数据（textSource.readLine(m_buffer, sizeof(m_buffer))）**

修改码 是处理文件的第一行数据，读取文件的基本信息。

其余的七种数据均直接调用readTable实现。

> 感觉seq的文件结构可能比raw要清晰得多？主要是数据种类少，并且没有筛选数据的步骤



### 适配到ZSystem

| 与PSSE_MemDb的接口（表名） | 与ZSystem的接口                                              | 用途                                                     |
| -------------------------- | ------------------------------------------------------------ | -------------------------------------------------------- |
|                            | system.setBaseMva(baseMva);                                  | 设置基准电压                                             |
| BUS                        | system.addNode(pNode)、system.setArea(pNode,areaName,areaName)、system.setZone(pNode,zoneName,zoneName)、system.setOwner(pNode,ownerName,ownerName)、system.addBusbar(pBusbar)、system.addGroundBranch(nodeId,g,b,0.0,0.0) | 添加节点信息、设定地区、分区、所有者、添加母线和接地支路 |
| FIXED_BUS_SHUNT            | system.addGroundBranch(nodeId,g,b,0.0,0.0)                   | 添加接地支路                                             |
| LOAD                       | system.addLoad(pLoad)、system.addGroundBranch(nodeId,g,b,0.0,0.0) | 添加负荷 和 接地支路                                     |
| GENERATOR                  | system.addGen(pGen);                                         | 添加发电机                                               |
| LINE                       | system.addBranch(pBranch);                                   | 添加支路信息                                             |
| TRANSFORMER                | system.addBranch(pBranch);                                   | 添加变压器支路信息                                       |
| SWITCHED_SHUNT             | system.addCap(pCap);                                         | 添加可投切并联补偿器                                     |

注意：BUS和LOAD添加接地支路都是有条件的，当shuntG ！= 0.0 && shuntB ！= 0.0