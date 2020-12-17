主要修改：

- cime ACLineSegment线路表
  - x>>>xPu
  - r>>>rPu
  - bch>>>bchPu
- cime TransformerWinding绕组表
  - x>>>xPu
  - r>>>rPu
- cime RectifierInverter >>> Cvt换流器表（修改文件
  - pathName>>>name
  - bridges>>>numBridge
  - BaseVoltage>>>acvolType
  - I_node>>>dcnode_id1
  - J_node>>>dcnode_id2
  - Z_node>>>node_id
- dt Disconnector刀闸表（修改文件
  - 开关ID》》》刀闸ID
  - 开关名称》》》刀闸名称

缺少的表：

- VoltageLevel（因为没有电压等级表 所以所有表都没有这个域）

- TapChangerType

