# 江西暂态故障

## 一期需求（线路为主）

主要是220线路故障、220+500同杆线路故障

### 500kV同杆线路异名相间短路故障

500kV同杆线路异名相间短路故障，重合闸失败，切除双回线； 

【注意以下线路的近侧指故障位置1%，远侧指故障位置99%】
1.对双回线要建立两张单相短路接地故障卡，故障时间从0秒开始，到100秒（默认值，可修改）结束；
2.再对双回线各自建立两张单相断线故障及重合闸近侧及远侧的故障卡，故障类型选择单相断线，相名与前面单相短路接地故障保持一致；近侧故障开始时间0.09秒，故障结束时间0.89秒；远侧故障开始时间0.1秒，故障结束时间0.9秒；
3.再对双回线各自建立两张线路三相断线故障卡，近侧故障开始时间0.98秒，故障结束时间同1中的结束时间；远侧故障开始时间1秒，故障结束时间同1中的结束时间；
以上一共十张故障卡。

### 220kV同杆线路异名相间短路故障

220kV同杆线路异名相间短路故障，重合闸失败，切除双回线

1.对双回线要建立两张单相短路接地故障卡，故障时间从0秒开始，到100秒（默认值，可修改）结束；
2.再对双回线各自建立两张单相断线故障及重合闸近侧及远侧的故障卡，故障类型选择单相断线，相名与前面单相短路接地故障保持一致；近侧故障开始时间0.12秒，故障结束时间1秒；远侧故障开始时间0.12秒，故障结束时间1秒；
3.再对双回线各自建立两张线路三相断线故障卡，近侧故障开始时间1.2秒，故障结束时间同1中的结束时间；远侧故障开始时间1.2秒，故障结束时间同1中的结束时间；
以上一共十张故障卡。

### 220kV线路开关拒动

三相短路，开关拒动，故障设置过程：

1.选择某220kV线路；
2.找到该线路故障侧的母线【判断该母线是单母线还是双母线，双母线需要考虑3中的c项动作，单母线则不考虑】
3.a.设置该母线ABC三相故障，0-0.1秒；
  b.设置该母线A相故障0.1秒-100秒（默认值，可修改）
  c.设置该母线母联开关三相断开，0.4-100秒（默认值，可修改） 【注意以上，设置默认故障位置1%，但是主变故障的默认故障位置为0%，可支持修改】
  d.设置该母线上所有设备三相断开，0.65秒-100秒【注意，设置默认故障位置1%，但是主变故障的默认故障位置为0%或者100%】



## 一期修改（构建江西特色的模板）

### 江西暂态故障模板（FaultTemplate_Jx）

根据江西的暂态故障新需求，构建了江西暂态故障模板

包括 线路1、线路2首端末端故障点的起止时间和故障类型还有故障相位（主要是针对同杆线路故障）

主变三侧的故障位置和故障时间（针对普通主变故障）

母联开关的首端和末端故障位置和故障时间（220线路的母联开关）

关联故障线路 和 关联故障主变（220线路开关拒动时 线路所在母线的关联支路（线路和主变））



综上所述，修改了代码中使用到故障模板的全部位置



## 二期需求（母线为主，批量设置）

220母线，500母线，全站全停

### 220kv母线 开关单相拒动

220母线开关单相拒动有两种情况：

#### 一、假如220KV母线为双母线，

单相拒动的线路连在Ⅰ段母线上，故障时序如下：

（1）0-0.1秒，Ⅰ段母线ABC三相故障；

（2）0.1-100秒，Ⅰ段母线A相故障；

（3）0.4-100秒，220kV母联开关ABC三相断开；

（4）0.65-100秒，Ⅰ段母线其他开关ABC三相断开；

#### 二、假如220kV母线为单母线，

因为没有母联开关，故（3）没有。

#### 三、批量故障

将全部220母线加入故障集，在扫描设备时分别对单母线和双母线进行分类处理。



### 500kV母线 开关单相拒动

对于500母线的所有虚拟分串，分别进行故障，500母线串的拓补连接情况如下：

其中i侧是500母线故障侧，j侧是另一侧，需要根据支路实际连接情况判断故障点位置和开断的位置

#### 一、完整串（不连高抗开关）线路+线路

1. 0-0.1秒，线路甲i侧母线三相故障；（短路故障点位置为2%）

2. 0.1-0.4秒，线路甲i侧母线A相故障，线路甲i侧B、C相断开；

3. 0.1-100秒，线路甲j侧三相断开；

4. 0.4-100秒，线路甲i侧三相断开，线路乙i侧、j侧三相断开（断开线路、开关支路故障点位置设在1%或99%）。

#### 二、完整串（不连高抗开关）线路+主变

1. 0-0.1秒，线路甲i侧母线三相故障；（短路故障点位置为2%）

2. 0.1-0.4秒，线路甲i侧母线A相故障，线路甲i侧B、C相断开；

3. 0.1-100秒，线路甲j侧三相断开；

4. 0.4-100秒，线路甲i侧三相断开，主变乙三相断开（断开主变支路故障点设置只能为0%或100%）。

（注：主变支路三相断开方式：高、低压侧在非中性点一侧母线断开，中压侧在中性点母线断开。

例如：高压侧（赣南昌1B-赣南昌500b）在500母线侧三相断线，低压侧（赣南昌1B-赣南昌1B35）在35母线侧断线，中压侧（赣南昌1B220-赣南昌220-2A）在主变虚拟母线侧（赣南昌1B220）断线）。

#### 三、完整串（连接高抗开关）线路+开关

线路甲带高抗，线路乙不带高抗，线路甲与线路乙同串。

A点：开关靠近故障母线的一侧；

B点：线路连接开关，靠近故障母线的一侧

C点：线路远离故障母线、开关的一侧

1. 0-0.1秒，线路甲i侧母线三相故障；（短路故障发生在线路甲上，故障位置在B点（线路连接开关，且靠近故障母线的一侧）

2. 0.1-0.4秒，线路甲i侧母线A相故障（线路单相短路，故障点在线路甲的B点），线路甲i侧B、C相断开（B、C相开断，开断位置为A点）；

3. 0.1-100秒，线路甲j侧三相断开（线路三相开断，开断位置为C点）；

4. 0.4-100秒，线路甲i侧三相断开（三相断开，开断位置在高抗的0%处），线路乙i侧、j侧三相断开（线路乙不带高抗切除位置为2%和99%）。

#### 四、不完整串 线路

1. 0-0.1秒，线路甲i侧母线三相故障；（短路故障点位置为2%）

2. 0.1-0.4秒，线路甲i侧母线A相故障，线路甲i侧B、C相断开；

3. 0.1-100秒，线路甲j侧三相断开；

4. 0.4-100秒，线路甲i侧三相断开。

#### 五、不完整串 主变

1. 0--0.4秒，主变高压侧三相短路（短路故障点位置为 0%）；
2. 0.4-100秒，主变甲高压侧三相断开（100%）。
3. 0.4-100秒，主变高中低三侧三相断开（0% 100%）。



### 220kV厂站 全站全停故障

全站全停故障分为 网络故障设置 和 节点扰动设置两部分：

#### 一、网络故障设置

设置此站内连接的任一【线路】，在2%处发生三相短路故障，故障时间为1-1.12s。

例如雷公山站的设置为赣雷公山-赣东江线，设置故障点位置为2%处，故障类型为三相短路接地，故障时间为1s-1.12s。

#### 二、节点扰动设置：

设置此站内所有【主变】【线路】【电容器】【电抗器】做【切线路】类型的节点扰动。

判别类型为【时间】，判别值【1.12s】，开始时间【0】，结束时间【10】。

电容器，电抗器的切除比率为1，线路和主变的切除比率为0。



## 二期修改（增加psasp的故障类型，增加分区筛选）

### 一、母线故障

使用TemplateType中bpa相同的分等级模式，只是在psasp界面启用时也增加了该类型

并且在ui中添加母线故障的过程

### 二、厂站故障

- 1.故障类型

  新增厂站E_Template_Substation故障类型，并且添加110厂站，220厂站，500厂站为电压等级

- 2.模板设置过程

  厂站故障做成在界面上选择厂站，代码同时处理网络故障和节点扰动的模式

- 3.节点扰动

  节点扰动中添加了“切线路”的模式，同步修改了节点扰动的e文件 和 节点扰动界面

### 三、分区筛选

在故障模板中添加了分区的存储，生成故障集的时候会判断节点分区是否为当前存储的分区