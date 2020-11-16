[TOC]

## 基本卡

### **PSASPDATA** PSASP软件版本、文件版本信息

### **DEV.LINE** 线路信息

线路名称、第一段单位正序电阻有名值、第一段单位正序电抗有名值、第一段单位正序电纳有名值、第一段单位零序电阻有名值、第一段单位零序电抗有名值、第一段单位零序电纳有名值、第一段长度、第一段线路类型、第二段单位正序电阻有名值、等等以此类推，共有五段。

### **DEV.SC** 串补相关信息

### **DEV.XFRM** 绕组信息

所有主变绕组（包括换流站主变）的短路、空载损耗以及空载电流百分比、短路电压百分比（三圈变拆分成3个绕组）。

### **DEV.SHUNT** 重庆地区并联电容电抗器

重庆地区所有的并联电容电抗器（低压容抗器、线路高抗、零序负荷）的额定电压、额定容量、容抗器类型（电容器为1，电抗器与零序负荷为2）。 

### **DEV.SECTION ** 断面相关信息



## 潮流卡

### **DATALIB.DAT** 数据文件（潮流计算必需） 

```
已对应的数据和表字段：
#版本号 汇总表
各个表的数量汇总信息
i5 *65

#,GEN,发电机参数，
参数组号	Sp(MVA)	Xd(p.u)	X'd(p.u.)	X"d(p.u.)	Xq(p.u.)	X'q(p.u.)	X"q(p.u.)	X2(p.u.)	Ra(p.u.)	T'd0(sec.)	T"d0(sec.)	T'q0(sec.)	T"q0(sec.)	Tj(sec.)	饱和a	饱和b	饱和n	阻尼(sec.)	简要注释
(i10 f15/6 *17 s)

#,AVR1,1型调压器参数，
参数组号	量测Kr	量测Tr(sec.)	放大Ka	放大Ta(sec.)	反馈Kf	反馈Tf(sec.)	励磁Te(sec.)	Efdmax(p.u.)	Efdmin(p.u.)	简要注释
(i10 f15/6 *9 s)

#,AVR2,2型调压器参数，
参数组号	量测Kr	量测Tr(sec.)	环节类型	T1(sec.)	T2(sec.)	T3(sec.)	T4(sec.)	放大Ka	放大Ta(sec.)	自励电压Kpt	自励电流Kit	换弧Ke	Efdmax(p.u.)	Efdmin(p.u.)	Vta(p.u.)	Vtb(p.u.)	简要注释
(i10 f15/6 *2 i5 f15/6 *13 s)

#,GOV1,调速器参数，
参数组号	调速器类型	调差δi	伺服机构Ts(sec.)	死区ε	配压阀σmax	配压阀σmin	开度μmax	开度μmin	蒸气容积T0(sec.)	水锤效应Tw(sec.)	过热系数α	中间过热Trh	量测环节Kδ	软负反馈Kβ	软负反馈Ti	简要注释

#,MOTO,感应电动机参数，
参数组号	转子R2(p.u.)	转子X2(p.u.)	转子T'dol(sec.)	转子惯性Tj1(sec.)	定子X1(p.u.)	阻力矩Kα	阻力矩p	滑差S0(p.u.)	Fp	Fq	简要注释

#,PSS1,PSS参数，
参数组号	Kω	Kp	kV	环节类型	Tq(sec.)	T1(sec.)	T2(sec.)	T3(sec.)	T4(sec.)	Vsmax(p.u.)	Vsmin(p.u.)	简要注释

#,LOAD,负荷静特性参数，
参数组号	Ap	Bp	Cp	Fp	Np	Aq	Bq	Cq	Fq	Nq	简要注释

#,DC,直流线调节器参数，
参数组号	K	T1(sec.)	T2(sec.)	T3(sec.)	简要注释

#,AVR310,3-10型调压器参数，
参数组号	调差电抗	量测Tr(sec.)	直流增益K	选择因子kV	串联校正T1(sec.)	串联校正T2(sec.)	串联校正T3(sec.)	串联校正T4(sec.)	功率增益Ka	功率Ta(sec.)	放大输出Vamax	放大输出Vamin	并联增益Kf	并联Tf(sec.)	比例反馈系数KH1	调节器增益Kb	调节器T5(sec.)	调节器Vrmax	调节器Vrmin	励磁机自励Ke	励磁机Te(sec.)	励磁机Vemax	励磁机C1(sec.)	励磁机C2(sec.)	负荷系数Kc	去磁系数Kd	efdmax	串联(0)/并联PID(1)	串联PID最大Vmax1	串联PID最大Vmin1	并联PID最大Vmax2	并联PID最小Vmin2	接入位置lelocation	欠励限制模型lemodel	参数组号leparno	接入位置oelocation	过励限制模型oemodel	参数组号oeparno	接入位置oilocation	定子过电流模型oimodel	参数组号oiparno	简要注释

#,AVR1112,11-12型调压器参数，
参数组号	调差电抗	量测Tr(sec.)	直流增益K	选择因子kV	串联校正T1(sec.)	串联校正T2(sec.)	串联校正T3(sec.)	串联校正T4(sec.)	功率增益Ka	功率Ta(sec.)	放大输出Vamax	放大输出Vamin	并联增益Kf	并联Tf(sec.)	调节器Vrmax	调节器Vrmin	负荷系数Kc	PSS输入位置	串联(0)/并联PID(1)	串联PID最大Vmax1	串联PID最大Vmin1	并联PID最大Vmax2	并联PID最小Vmin2	接入位置lelocation	欠励限制模型lemodel	参数组号leparno	接入位置oelocation	过励限制模型oemodel	参数组号oeparno	接入位置oilocation	定子过电流模型oimodel	参数组号oiparno	简要注释

#,PSS2,2型PSS参数，
参数组号	kω	kp	kt	Tr(sec.)	Tw1(sec.)	Tw2(sec.)	T1(sec.)	T2(sec.)	T3(sec.)	T4(sec.)	T5(sec.)	T6(sec.)	Vsmax(p.u.)	Vsmin(p.u.)	简要注释

#,CLOAD,综合负荷参数，
参数组号	定子电阻	定子电抗	激磁电抗	转子电阻	转子电抗	惯性时间常数	机械转矩方程常数A	机械转矩方程常数B	感应电机初始有功比例	初始负荷率	有功恒阻抗比例	有功恒电流比例	无功恒阻抗比例	无功恒电流比例	简要注释

#,AVR13,13型调压器参数，
参数组号	调差电阻Rc	调差电抗Xc	量测Tr(sec.)	Vimax(p.u.)	Vimin(p.u.)	滞后时间Tb(sec.)	超前时间Tc(sec.)	放大Ka	放大Ta(sec.)	Vrmax(p.u.)	Vrmin(p.u.)	反馈Kf	反馈Tf(sec.)	换相因子Kc	Efdmax(p.u.)	Efdmin(p.u.)	简要注释

#,AVR14,14型调压器参数，
参数组号	调差电阻Rc	调差电抗Xc	量测Tr(sec.)	增益Ka	时间Ta	比例增益Kp	积分系数Ki	最大输出Vrmax	最小输出Vrmin	比例增益IKP	积分系数IKI	电流环Vfmax	电流环Vfmin	可控硅增益	可控硅时间常数	反馈放大倍数Kifd	反馈时间常数Tifd	Efdmax（p.u.）	Efdmin（p.u.）	简要注释

#,AVR15,15型调压器参数，
参数组号	发电机定子电阻	d轴同步电抗	q轴同步电抗	d轴暂态电抗	自并励励磁系统惯性时间常数	Δδ的调节系数	ΔPe的调节系数	Δω的调节系数	电压偏差ΔVt的比例系数	电压偏差ΔVt的积分系数	电压偏差ΔVt的微分系数	转动惯量(秒)	定子开路时励磁绕组时间常数(秒)	隔直环节时间常数	励磁电压上限	励磁电压下限	简要注释

#,AVR16,16型调压器参数，
参数组号(Par_No)	测量环节时间常数(Tr)	调差系数(Kc1)	与换相电抗相关的整流器负荷系数(Kc2)	发电机电压为额定值时调节器输出上限(Vrmax)	发电机电压为额定值时调节器输出下限(Vrmin)	串联校正环节的直流增益(K)	积分校正选择因子(Kv)	串联校正环节时间常数(T1,单位为秒)	串联校正环节时间常数(T2,单位为秒)	串联校正环节时间常数(T3,单位为秒)	串联校正环节时间常数(T4,单位为秒)	功率放大环节增益(Ka)	功率放大环节时间常数(Ta,单位为秒)	校正环节上限福(Vmax)	校正环节下限福(Vmin)	放大环节输出上限(Vamax,标幺值)	放大环节输出下限(Vamin,标幺值)	并联校正环节增益(Kf)	并联校正环节时间常数(Tf,单位为秒)	低比门闭锁值(Lkp,必须为正值)	高比门闭锁值(Lkn,必须为负值)	接入位置(hlction)	过励限制调节增益(Kh)	超前滞后时间常数(Th1)	超前滞后时间常数(Th2)	发电机磁场最大允许电流值(Ifmax)	发电机磁场长期允许电流(Ifc,标幺值)	发电机磁场电流限值(Ifl)	过热系数(B)	过热返回系数(Kfh)	接入位置(Lction)	电压补偿投退(swl)	无功信号超前滞后时间常数(Tl1)	无功信号超前滞后时间常数(Tl2)	串联校正环节时间常数(Tl3,单位为秒)	串联校正环节时间常数(Tl4,单位为秒)	一阶滞后时间常数(Tlu)	串联校正环节的直流增益(Kl)	积分校正选择因子(Klv)	低励限制调节上限幅(Vuelmax)	低励限制调节下限幅(Vuelmin)	低励限制曲线上第一点的有功功率(PL1,标幺值)	低励限制曲线上第一点的无功功率(QL1,标幺值)	低励限制曲线上第二点的有功功率(PL2,标幺值)	低励限制曲线上第二点的无功功率(QL2,标幺值)	低励限制曲线上第三点的有功功率(PL3,标幺值)	低励限制曲线上第三点的无功功率(QL3,标幺值)	低励限制曲线上第四点的有功功率(PL4,标幺值)	低励限制曲线上第四点的无功功率(QL4,标幺值)	低励限制曲线上第五点的有功功率(PL5,标幺值)	低励限制曲线上第五点的无功功率(QL5,标幺值)	接入位置(DLction)	定子电流限制超前滞后时间常数(Td1,单位为秒)	定子电流限制超前滞后时间常数(Td2,单位为秒)	调节增益(Kd)	定子电流限制值(Itl)	定子电流长期运行值(Itc)	过热系数(Bd)	返回系数(Kth)	无功信号超前滞后时间常数(Tq1,单位为秒)	无功信号超前滞后时间常数(Tq2,单位为秒)	串联校正时间常数(Tq3,单位为秒)	串联校正时间常数(Tq4,单位为秒)	有功信号一阶滞后时间常数(Tu,单位为秒)	串联校正环节的直流增益(Kq)	积分校正选择因子(Kqv)	延迟时间(Tdy,单位为秒)	保持时间(Tsf,单位为秒)	定子过负荷限制调节上限幅(Voelmax)	定子过负荷限制调节下限幅(Voelmin)	过励限制曲线上第一点的有功功率(Ph1,标幺值)	过励限制曲线上第一点的无功功率(Qh1,标幺值)	过励限制曲线上第二点的有功功率(Ph2,标幺值)	过励限制曲线上第二点的无功功率(Qh2,标幺值)	过励限制曲线上第三点的有功功率(Ph3,标幺值)	过励限制曲线上第三点的无功功率(Qh3,标幺值)	过励限制曲线上第四点的有功功率(Ph4,标幺值)	过励限制曲线上第四点的无功功率(Qh4,标幺值)	过励限制曲线上第五点的有功功率(Ph5,标幺值)	过励限制曲线上第五点的无功功率(Qh5,标幺值)	简要注释

#,GOV2,2型调速器参数，
参数组号	转速放大倍数	死区ε	滑阀时间	中间滑阀时间	开启时间常数	关闭时间常数	最大关闭速度	最大开启速度	原动机最大输出	原动机最小输出	蒸汽容积时间	高压缸比例	再热器时间	中压缸比例	交叉管时间	低压缸比例	自然过调系数	过热器时间	汽包蓄热时间	锅炉燃料释放	管道流量	延时	主汽最大值	主汽最小值	简要注释

#,GOV3,3型调速器参数，
参数组号	死区ε	转速偏差放大倍数	转速变换时间常数	负荷自动开关	负荷比例倍数	负荷微分倍数	负荷积分倍数	负荷积分上限	负荷积分下限	负荷控制上限	负荷控制下限	负荷前馈开关	一次调频负荷上限	一次调频负荷下限	调节级自动开关	调节级比例倍数	调节级微分倍数	调节级积分倍数	调节级积分上限	调节级积分下限	调节级输出上限	调节级输出下限	控制环节输出上限	控制环节输出下限	关闭时间常数	开启时间常数	最大关闭速度	最大开启速度	原动机最大输出	原动机最小输出	油动机反馈时间	比例放大倍数	微分倍数	积分倍数	积分上限	积分下限	输出上限	输出下限	蒸汽容积时间	高压缸比例	再热器时间	中压缸比例	交叉管时间	低压缸比例	自然过调系数	过热器时间	汽包蓄热时间	锅炉燃料释放	管道流量	延时	主汽最大值	主汽最小值	T4	简要注释

#,GOV4,4型调速器参数，
参数组号	转速测量时间	死区ε	转速偏差放大倍数	控制方式选择	调节比例倍数	调节微分倍数	调节积分倍数	调节积分上限	调节积分下限	调节PID上限	调节PID下限	负荷控制前馈系数	一次调频负荷上限	一次调频负荷下限	关闭时间常数	开启时间常数	最大关闭速度	最大开启速度	原动机最大输出	原动机最小输出	油动机反馈时间	比例放大倍数	微分倍数	积分倍数	积分上限	积分下限	输出上限	输出下限	蒸汽容积时间	高压缸比例	再热器时间	中压缸比例	交叉管时间	低压缸比例	自然过调系数	过热器时间	汽包蓄热时间	锅炉燃料释放	管道流量	延时	主汽最大值	主汽最小值	T4	简要注释

#,GOV5,5型调速器参数，
参数组号	滤波器时间	转速偏差死区	转速偏差方式	转速偏差放大	主汽压力偏差放大	控制方式选择	调节比例倍数	调节微分倍数	调节积分倍数	调节积分上限	调节积分下限	调节PID上限	调节PID下限	一次调频负荷上限	一次调频负荷下限	关闭时间常数	开启时间常数	最大关闭速度	最大开启速度	原动机最大输出	原动机最小输出	油动机反馈时间	比例放大倍数	微分倍数	积分倍数	积分上限	积分下限	输出上限	输出下限	蒸汽容积时间	高压缸比例	再热器时间	中压缸比例	交叉管时间	低压缸比例	自然过调系数	过热器时间	汽包蓄热时间	锅炉燃料释放	管道流量	延时	主汽最大值	主汽最小值	T4	简要注释

#,GOV6,6型调速器参数，
参数组号	pmax	Ar	t1	t2	t3	t4	t5	Af	简要注释

#,GOV7,7型调速器参数，
参数组号	TYPE1	TYPE2	TYPE3	T1	TR1	DB1	DB1MAX	DB1MIN	KW	T2	TR2	EP	DB2	DB2MAX	DB2MIN	T3	TR3	BP	DB3	DB3MAX	DB3MIN	KP	KD	KI	TD	INTMAX	INTMIN	PIDMAX	PIDMIN	YC	TC	TO	VELC	VELO	PMAX	PMIN	TF	KP1	KD1	KI1	INTMAX1	INTMIN1	PIDMAX1	PIDMIN1	T4	Tw	Kwtype	At	Tr	YNL	DBWP	DBWN	pchoice	promax1	promin1	promax2	promin2	ratelimp	ratelimn	简要注释

#,GOV8,8型调速器参数，
参数组号	T1	TR1	DB1P	DB1N	MAX1	MIN1	Rti1	Rtd1	mode	T2	TR2	EP	DB2	MAX2	MIN2	Rti2	Rtd2	Kp1	Ki1	Kd1	Td1	Intmax1	Intmin1	Pidmax1	Pidmin1	NMC	NPA	T3	TR3	BP	DB3	MAX3	MIN3	Kp2	Ki2	Kd2	Td2	INTMAX2	INTMIN2	PIDMAX2	PIDMIN2	KW	wcp	wcn	Dbip	Dbin	Tdy1	Tdy2	Maxi	Mini	Kpi	Kii	Kdi	bpi	Kp	Kd	Ki	Intmax	Intmin	Pidmax	Pidmin	Tc	Topen	Tf	Tdy	VELC	VELO	PMAX	PMIN	Y1	Q1	Y2	Q2	Y3	Q3	A	B	Tw	Rti0	Rtd0	Dp1	Dp2	Tqm	Kp3	Ki3	Kd3	Td3	DBhp	T4	简要注释

#,GOV9,9型调速器参数，
参数组号	转速测量时间	死区ε	转速偏差放大倍数	控制方式选择	调节比例倍数	调节微分倍数	调节积分倍数	调节积分上限	调节积分下限	调节PID上限	调节PID下限	负荷控制前馈系数	一次调频负荷上限	一次调频负荷下限	关闭时间常数	开启时间常数	最大关闭速度	最大开启速度	原动机最大输出	原动机最小输出	油动机反馈时间	比例放大倍数	微分倍数	积分倍数	积分上限	积分下限	输出上限	输出下限	蒸汽容积时间	高压缸比例	再热器时间	中压缸比例	交叉管时间	低压缸比例	自然过调系数	过热器时间	汽包蓄热时间	锅炉燃料释放	管道流量	延时	主汽最大值	主汽最小值	机械功率量测时间常数	电磁功率量测时间常数	延时1	延时2	延时3	上升速率限制	下降速率限制	简要注释

#,GOV10,10型调速器参数，
参数组号	T1	TR1	Kw	DB1P	DB1N	DMAX1	DMIN1	Kp	Ki	Kd	Tv	Imax	Imin	PIDmax	PIDmin	mode	pflag	bpflag	T2	TR2	DigiSamp	Ep	Rr	Rf	DB2P	DB2N	DBMAX2	DBMIN2	T3	TR3	P1	P2	P3	Kp21	Ki21	Kd21	Td21	Kp22	Ki22	Kd22	Td22	Kp23	Ki23	Kd23	Td23	Imax2	Imin2	PIDmax2	PIDmin2	Fh	FL	Tdelay	Tmode	Kps	Kis	Kds	Imaxs	Imins	Pidmaxs	Pidmins	Tos	Tcs	VELclose	VELopen	DBsP	DBsN	Psmax	Psmin	T2s	T3s	T4s	Yy1	Q1	Yy2	Q2	Yy3	Q3	Kp1	Kp2	Kr	A	B	Tw	Kpj	Kij	Kdj	Imaxj	Iminj	Pidmaxj	Pidminj	Toj	Tcj	VELclosej	VELopenj	DBjP	DBjN	Pjmax	Pjmin	T2j	T3j	T4j	X1	Y1	X2	Y2	X3	Y3	X4	Y4	X5	Y5	X6	Y6	X7	Y7	X8	Y8	X9	Y9	X10	Y10	bp	nsource	简要注释

#,PSS3,3型PSS参数，
参数组号	输出放大倍数Kp	K0	K1	K2	K3	隔直环节时间常数2	移相时间常数T1(sec.)	移相时间常数T2(sec.)	移相时间常数T3(sec.)	输出限幅Vsmax(p.u.)	输出限幅Vsmin(p.u.)	隔直环节时间常数1	转速偏差放大倍数	电功率偏差放大倍数	加速功率放大倍数	隔直环节类型	K4	移相时间常数T4(sec.)	简要注释

#,PSS4,4型PSS参数，
参数组号	Trw	T5	T6	T7	Kr	Trp	Tw	Tw1	Tw2	Ks	T9	T10	T12	Kw	Kp	T1	T2	T13	T14	T3	T4	VSMAX	VSMIN	简要注释

#,PSS5,5型PSS参数，
参数组号	量测时间T1	量测时间T2	隔直T3	隔直T4	隔直T5	放大倍数A	相位	速度放大倍数	速度时间常数	加速度放大	放大倍数K	VSMAX	VSMIN	简要注释

#,PSS7,7型PSS参数，
参数组号	La	Lb	Lc	Ca	Cb	Cd	Cf	T1	KL	KL1	KL2	KL3	KL4	TL1	TL2	TL3	TL4	TL5	TL6	TL7	TL8	TL9	TL10	TL11	TL12	VLmax	VLmin	KI	KI1	KI2	KI3	KI4	TI1	TI2	TI3	TI4	TI5	TI6	TI7	TI8	TI9	TI10	TI11	TI12	VImax	VImin	KH	KH1	KH2	KH3	KH4	TH1	TH2	TH3	TH4	TH5	TH6	TH7	TH8	TH9	TH10	TH11	TH12	VHmax	VHmin	VSmax	VSmin	简要注释

#,SVC1,1型静止无功补偿器参数，
参数组号	放大K1	可调ΔBmax(p.u.)	可调ΔBmin(p.u.)	等值Bmax(p.u.)	等值Bmin(p.u.)	放大T1(sec.)	量测Tm(sec.)	整流器Tth(sec.)	简要注释

#,SVC2,2型静止无功补偿器参数，
参数组号	Xs(p.u.)	Xc(p.u.)	电流过载Ip	延迟T(sec.)	简要注释

#,SVC3,3型静止无功补偿器参数，
参数组号	TS1	VEMAX	TS2	TS3	A	B	TS4	TS5	KSVS	KSD	BMAX	BMAXP	BMINP	BMIN	TS6	DV	KS1	TS7	TS8	TS9	AP	BP	TS13	TS14	TS15	TS16	KS3	VSCSMAX	IERR	KS2	TS10	TS11	TS12	Vscsmin	简要注释

#,SVC4,4型静止无功补偿器参数，
参数组号	K1	T1	Ksvs1	Ts1	Ts2	Ts3	Ts4	K2	T3	Ksvs2	Ts5	Ts6	Ts7	Ts8	Vl	Pl	Td	Tsf	T2	Bmax	Bmin	Tsw	Vemax	Vemin	Kitg1	Vimax	Vimin	Twp	Pemax	Pemin	Kitg2	Pimax	Pimin	Qcomp	Vcomp	Pcomp	Tvcomp	Tpcomp	Vquit	Pquit	Tvquit	Tpquit	Modeqt	QBquit	简要注释


#,DC1,5型直流调节器参数，
参数组号	G_amax	T_amax	Gammaref	Gammamin	Kp_vca	Ti_vca	K1_ra	K2_ra	CDL	DL	Decr	T_ga	Td_ret	Th_ret	Th_res	mode	LEAD	FP_CO	BC_ON	Udlow	Udhigh	Udtup	Udtdn	Iomin_vdcL	Iomin	Id_t	Gain	Kp	Ti	G_cf	K_cf	T_dn_cf	Alpha_res	U_Enable	UK	Gama_fail	Iovs	Tovs	Iovl	Tovl	Tflock	Cfo_f	Cfo_comdy	Cfo_Iomin	Cfo_amax	Cfo_srt	Cfo_Vth	Cfo_idt	Cfo_rdt	Cfo_dcb	简要注释


#,TCSC,固定/可控串补参数，
参数组号	Kap	Tap	Twp	T1p	T2p	T3p	T4p	Kav	Tav	Twv	T1v	T2v	T3v	T4v	Ta1	Tb1	KXc01	Kpp	Ttcsc	X_max	X_min	IN	Ib	Xc0	Alfa	功率输入死区	电压输入死区	Iquit	Tquit	Iopen	Topen	Ta2	Tb2	Ta3	Tb3	Ta4	Tb4	Ta5	Tb5	串补类型	是否考虑MOV动作	串补中电容器保护水平倍数	MOV能量限制值	能量增长速度限制	串补支路最大电流限制	串补重投时刻	串补重投延迟时间	串补重投最大线路电流限制	串补重投最大线路电流延迟时间	断线串补重投标志	简要注释


#,WGMOT,鼠笼异步风电机组参数，
参数组号	GRATEPOWER	WINDPOWER_MODEL	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	TURBINE_RADIUS	AXIS_FLEX	AXIS_DAMP	OMEGA_BASE	OMEGA_BASE_T	TJ_TURBINE	TJ_GEN	TH	RHO	OMEGA_RATE	VWIND_CI	VWIND_CO	VWIND_RATE	VWIND0	TURBINE_MODEL	R2	X2	X1	TD01	简要注释

#,WGGE,双馈直驱通用风电机组参数，
参数组号	GRATEPOWER	WINDPOWER_MODEL	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	TURBINE_RADIUS	AXIS_FLEX	AXIS_DAMP	OMEGA_BASE	OMEGA_BASE_T	TJ_TURBINE	TJ_GEN	TH	RHO	OMEGA_RATE	VWIND_CI	VWIND_CO	VWIND_RATE	VWIND0	TURBINE_MODEL	KPP	KIP	TP	THETAMAX	THETAMIN	DTHETAMAX	DTHETAMIN	PMAX	PMIN	DPMAX	DPMIN	KPC	KIC	KPTRQ	KITRQ	TPC	TR	TV	KPV	KIV	KQI	KVI	QMAX	QMIN	XIQMAX	XIQMIN	VMAX	VMIN	IPMAX	QMOD	COSPHI	TCO	XPP	RL	XL	简要注释

#,SGEN,光伏电站，
参数组号	Im	Isc	Vm	Voc	Smax	Smin	Kiv	Kv	Tv	Ki2	Ki	Ti	Kpwm	TL	Imax	Imin	KF	TC	Amax	Amin	site	T	V1	V2	V3	V4	TV1	TV2	TV3	TV4	TvBACK	f1	f2	f3	f4	Tf1	Tf2	Tf3	Tf4	Tfback	I1	I2	Ti1	Ti2	Ti3	Tiback	V21	V22	Te1	Te2	Teback	Tback	Vtbase	isprct	Note


#,LE1,1型欠励限制模型，
参数组号	Tr	pmax	pmin	P1	Q1	P2	Q2	P3	Q3	P4	Q4	P5	Q5	P6	Q6	P7	Q7	uth	uat	tqa	dqr	Kq	T1	T2	Qcmax	Qcmin	qd	tqd	简要注释

#,VSC2,2型VSC换流器模型，
参数组号	cway	ctype	tr	k1	ki1	k2	ki2	idmax	idmin	iqmax	iqmin	idomax	idomin	iqomax	iqomin	dctype	altn	kpd1	kid1	kpd2	kid2	kpd3	kid3	kdd1	tdd1	kdd2	tdd2	fdbp	fdbn	id1max	id1min	ido1max	ido1min	id2max	id2min	ido2max	ido2min	id3max	id3min	ido3max	ido3min	udcrefl	udcrefh	ku	kp	qctype	kpq1	kiq1	iq1max	iq1min	kdq1	tdq1	iqo1max	iqo1min	isolt	ratphaf	Pll_kp	negnk	ak2pd	ak2id	a2mxid	a2mnid	a2mxd	a2mnd	ak2pq	ak21q	a2mxiq	a2mniq	a2mxq	a2mnq	a2limit	Vach	Vacl	Vdch1	Vdcl1	pcovup	tpcov	Aup1	tacbk	cbreak	tracv	trdc	Pll_ki	traci	dampr	cfreq	Vcacup	Vcaclw	vconup	vconlw	vbacup	vbaclw	distrqd	vacprup	vacprlw	vacbcup	vacbclw	frqprup	frqprlw	frqbcup	frqbclw	kpq2	kiq2	iq2max	iq2min	kdq2	tdq2	iqo2max	iqo2min	dcstep	Taup1	hmratio	hmdecra	tvach	tvacl	Vdch2	Vdcl2	tvdch1	tvdcl1	tvdch2	tvdcl2	Aup2	Taup2	Aup3	Taup3	Aupvl	Taupvl	Vunb1	Vunb2	tvunb1	tvunb2	Aunb1	Aunb2	taunb1	taunb2	trescon	timres	tresacc	tresval	trescre	fcovup	Tfcovup	fcovlw	Tfcovlw	tvcacup	tvcaclw	Alimcd1	kidw	Alimcd2	Ua1	Ua2	Kiupd	Puprat	Plwrat	Uduprat	Udlwrat	Rcharg	Rdiode	Quprat	Qlwrat	Uauprat	Ualwrat	dUacrefl	dUacrefh	Pzz1	Pzz2	Pzz3	Pzz4	Pzz5	Pzz6	Pzz7	Pzz8	Pzz9	Quu1	Quu2	Quu3	Quu4	Quu5	Quu6	Quu7	Quu8	Quu9	Qww1	Qww2	Qww3	Qww4	Qww5	Qww6	Qww7	Qww8	Qww9	Alimcq1	tua1	tpex1	tqex1	tvex1	Ub1	Uc1	Ud1	tuc1	Coupv	Ub2	tua2	Alimcq2	Uc2	tuc2	tdcvex1	Coupp	Forwp	Satup	Forwdcv	Satudcv	Forwq	Satuq	Follwq	Satuacv	Satuf	Vupin	Vlowin	Kiupq	tuefsmo	Ue1	Uf1	tue1	tuf1	tub1	tud1	tub2	tud2	Ud2	tpex2	tqex2	tvex2	tdcvex2	Alimfd1	Alimfq1	Alimfd2	Alimfq2	Ifaucd1	Ifaucq1	Ifaucd2	Ifaucq2	Ifaufd1	Ifaufq1	Ifaufd2	Ifaufq2	Ifausd1	Ifausq1	Ifausd2	Ifausq2	Iforb	R_acp	X_acp	Grp_acp	Vin_acp	Tin_acp	Vout_acp	Tout_acp	Rt_acp	Xt_acp	Ton_acp	Toff_acp	Contyp	Alim1	Alim2	Darfd1	Darfq1	Daefd2	Daefq2	Kupd0	fordplim	tbefupd	tlimfordp	Abslowa	Unlimq1	Unlimq2	CHGVACTR	Kpq3	Kiq3	Iqo3max	Iqo3min	Oppstr	Vchgrat	Kiupdx	Kiupqx	Kdcsca	Vmodup	Vmodlw	tmody	freqmd	tfreqs	Di1	Akp1	Di2	Akp2	Pco_kp	Lockun	Fconv	Fcont	Akvup0	Akvup	Linlimun	Uaclim1	Aclim1	Uaclim2	Aclim2	Uaclim3	Aclim3	Uaclim4	Aclim4	Uaclim5	Aclim5	Aciup	Udcoup	Udcolw	tUdco	Udcomg	incrdu	decrdu	Iconqv	Udcinup	Udcinlw	Tset_acp	back45	back46	简要注释


#,OE1,1型过励限制模型参数，
参数组号	kl1	ifdlim	ifdinf	B	C	T	kl2	tl1	tl2	valid1	valid2	简要注释


#,LE2,2型欠励限制模型参数，
参数组号	kl1	ifdlim	ifdinf	B	C	T	kl2	tl1	tl2	valid1	valid2	简要注释


#,DS4,直流频率调制器4型，
参数组号	Tr	Kr	Dfrmax	Dfrmin	Drplus	Drminus	Tr1	Tr2	Tr3	Tr4	Tr5	Kr1	Ti	Ki	Dfimax	Dfimin	Diplus	Diminus	Ti1	Ti2	Ti3	Ti4	Ti5	Ki1	Pmodmax	Pmodmin	简要注释

#,PSS8,8型PSS参数，
参数组号	Kqv	Tqv	TQ1	TQ1'	TQ2	TQ2'	TQ3	TQ3'	Vsmax	Vsmin	简要注释


#,DFIG2,2型双馈风力发电机，
参数组号	WTGMODEL	GRATEPOWER	OMEGA_BASE	TJ_GEN	Rs	Rr	Ls	Lr	Lm	Td0p	Lss	Lrr	Lp	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	VWIND_RATE	VWIND0	VWIND_CI	VWIND_CO	RHO	KB	rhoAr2	NWfflg	TURBINE_RADIUS	OMEGA_BASE_T	TJ_TURBINE	OMEGA_RATE	OMEGA_BASE_T_CONV	OMEGA_BASE_CONV	GRATEPOWER_CONV	NTURBINE_MODEL	AXIS_FLEX	AXIS_DAMP	dPord_max	dPord_min	Temax	Temin	dTemax	dTemin	Twgen	Twref	woffset	Kptrq	Kitrq	SpeedPeFlag	p1	spd1	p2	spd2	p3	spd3	p4	spd4	Kpw	Kiw	Kpc	Kic	Kcc	Ttheta	Thetamax	Thetamin	DThetamax	DThetamin	NWdinflg	Kwi	dbwi	Tlpwi	Twowi	urlwi	drlwi	Pmxwi	Pmnwi	Kptrq_Aft_WndInt	Kitrq_Aft_WndInt	Tpord_Aft_WndInt	NDBRflg	Ebst	Kdbr	VLin	VLout	VHin	VHout	VL1	VL2	TL1	TL2	VH1	VH2	TH1	TH2	NLVRTFLG	LVRTPORTION	HVRTPORTION	TdlyVLin	TdlyVLout	TdlyVHin	TdlyVHout	PQ_flag	PQ_LHVRT_FLAG	IpCLL_LHVRT_norm_FLAG	Vq1	Iq1	Vq2	Iq2	Vq3	Iq3	Vq4	Iq4	Vp1	Ip1	Vp2	Ip2	Vp3	Ip3	Vp4	Ip4	Tfltr	Trp	Trf	Trv	Freq_flag	Krp	PPOI_flag	fdb1	fdb2	Dup	Ddn	Dup_Pmax	Ddn_Pmin	Perrmax	Perrmin	Kp_pp	Ki_pp	Ppoimax	Ppoimin	Tlag	Vcmp_flag	PFPOI_flag	QPOI_flag	Rc	Xc	Kc	Vpdb1	Vpdb2	Verrmax	Verrmin	Kp_pv	Ki_pv	Qpdb1	Qpdb2	Qerrmax	Qerrmin	Kp_pq	Ki_pq	Qpoimax	Qpoimin	Tft	Tfv	Pmax	Pmin	Qmax	Qmin	dPmax	dPmin	dQmax	dQmin	Ip_max	Ip_min	Iq_max	Iq_min	I_max	I_min	Tg	P_flag	Tpord	Kp_lp	Ki_lp	Tip	Qref_flag	V_flag	Q_flag	Tqord	Tiq	Kp_lqv	Ki_lqv	V_max	V_min	Kp_lv	Ki_lv	Kp_lq	Ki_lq	Vldb1	Vldb2	Kqv	Iqinjh	Iqinjl	LVRT_IN_PFLAG	KP_LVRT	Pset_LV	K1_Ip_LV	K2_Ip_LV	Ipset_LV	VZEROX	VBRKPT	IpBRKPT	LVRT_IN_QFLAG	KQ_LV	Qset_LV	K1_Iq_LV	K2_Iq_LV	Iqset_LV	Ip_LVREC0_FLAG	KIp_LVREC0	Ipset_LVREC0	TLVRT_RECOVER0	Iq_LVREC0_FLAG	KIq_LVREC0	Iqset_LVREC0	HVRT_IN_PFLAG	KP_HV	Pset_HV	K1_Ip_HV	K2_Ip_HV	Ipset_HV	HVRT_IN_QFLAG	KQ_HV	Qset_HV	K1_Iq_HV	K2_Iq_HV	Iqset_HV	Ip_HVREC0_FLAG	KIp_HVREC0	Ipset_HVREC0	THVRT_RECOVER0	Iq_HVREC0_FLAG	KIq_HVREC0	Iqset_HVREC0	LVRT_RECOVER_PFLAG	dIp_RECOVER_max	Tcons_Precover	Ip_rec_a	Ip_rec_b	Ip_rec_c	Ip_rec_d	Ip_rec_t0	LVRT_RECOVER_QFLAG	Tcons_Qrecover	ICONTYP_UBL	IK1_Ip_LV_UBL	IK2_Ip_LV_UBL	IIpset_LV_UBL	IK3_Ip_LV_UBL	IK1_Iq_LV_UBL	IK2_Iq_LV_UBL	IIqset_LV_UBL	IK3_Iq_LV_UBL	LVRT_flag	HVLT_flag	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	简要注释

#,PMSG2,2型直驱风力发电机，
参数组号	WTGMODEL	GRATEPOWER	OMEGA_BASE	TJ_GEN	Rs	Rr	Ls	Lr	Lm	Td0p	Lss	Lrr	Lp	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	VWIND_RATE	VWIND0	VWIND_CI	VWIND_CO	RHO	KB	rhoAr2	NWfflg	TURBINE_RADIUS	OMEGA_BASE_T	TJ_TURBINE	OMEGA_RATE	OMEGA_BASE_T_CONV	OMEGA_BASE_CONV	GRATEPOWER_CONV	NTURBINE_MODEL	AXIS_FLEX	AXIS_DAMP	dPord_max	dPord_min	Temax	Temin	dTemax	dTemin	Twgen	Twref	woffset	Kptrq	Kitrq	SpeedPeFlag	p1	spd1	p2	spd2	p3	spd3	p4	spd4	Kpw	Kiw	Kpc	Kic	Kcc	Ttheta	Thetamax	Thetamin	DThetamax	DThetamin	NWdinflg	Kwi	dbwi	Tlpwi	Twowi	urlwi	drlwi	Pmxwi	Pmnwi	Kptrq_Aft_WndInt	Kitrq_Aft_WndInt	Tpord_Aft_WndInt	NDBRflg	Ebst	Kdbr	VLin	VLout	VHin	VHout	VL1	VL2	TL1	TL2	VH1	VH2	TH1	TH2	NLVRTFLG	LVRTPORTION	HVRTPORTION	TdlyVLin	TdlyVLout	TdlyVHin	TdlyVHout	PQ_flag	PQ_LHVRT_FLAG	IpCLL_LHVRT_norm_FLAG	Vq1	Iq1	Vq2	Iq2	Vq3	Iq3	Vq4	Iq4	Vp1	Ip1	Vp2	Ip2	Vp3	Ip3	Vp4	Ip4	Tfltr	Trp	Trf	Trv	Freq_flag	Krp	PPOI_flag	fdb1	fdb2	Dup	Ddn	Dup_Pmax	Ddn_Pmin	Perrmax	Perrmin	Kp_pp	Ki_pp	Ppoimax	Ppoimin	Tlag	Vcmp_flag	PFPOI_flag	QPOI_flag	Rc	Xc	Kc	Vpdb1	Vpdb2	Verrmax	Verrmin	Kp_pv	Ki_pv	Qpdb1	Qpdb2	Qerrmax	Qerrmin	Kp_pq	Ki_pq	Qpoimax	Qpoimin	Tft	Tfv	Pmax	Pmin	Qmax	Qmin	dPmax	dPmin	dQmax	dQmin	Ip_max	Ip_min	Iq_max	Iq_min	I_max	I_min	Tg	P_flag	Tpord	Kp_lp	Ki_lp	Tip	Qref_flag	V_flag	Q_flag	Tqord	Tiq	Kp_lqv	Ki_lqv	V_max	V_min	Kp_lv	Ki_lv	Kp_lq	Ki_lq	Vldb1	Vldb2	Kqv	Iqinjh	Iqinjl	LVRT_IN_PFLAG	KP_LVRT	Pset_LV	K1_Ip_LV	K2_Ip_LV	Ipset_LV	VZEROX	VBRKPT	IpBRKPT	LVRT_IN_QFLAG	KQ_LV	Qset_LV	K1_Iq_LV	K2_Iq_LV	Iqset_LV	Ip_LVREC0_FLAG	KIp_LVREC0	Ipset_LVREC0	TLVRT_RECOVER0	Iq_LVREC0_FLAG	KIq_LVREC0	Iqset_LVREC0	HVRT_IN_PFLAG	KP_HV	Pset_HV	K1_Ip_HV	K2_Ip_HV	Ipset_HV	HVRT_IN_QFLAG	KQ_HV	Qset_HV	K1_Iq_HV	K2_Iq_HV	Iqset_HV	Ip_HVREC0_FLAG	KIp_HVREC0	Ipset_HVREC0	THVRT_RECOVER0	Iq_HVREC0_FLAG	KIq_HVREC0	Iqset_HVREC0	LVRT_RECOVER_PFLAG	dIp_RECOVER_max	Tcons_Precover	Ip_rec_a	Ip_rec_b	Ip_rec_c	Ip_rec_d	Ip_rec_t0	LVRT_RECOVER_QFLAG	Tcons_Qrecover	ICONTYP_UBL	IK1_Ip_LV_UBL	IK2_Ip_LV_UBL	IIpset_LV_UBL	IK3_Ip_LV_UBL	IK1_Iq_LV_UBL	IK2_Iq_LV_UBL	IIqset_LV_UBL	IK3_Iq_LV_UBL	LVRT_flag	HVLT_flag	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	简要注释

#,PMAC,调相机附加控制模型参数，13
参数组号	Tr'	T1	T2'	Kh	Kq	Kv'	Ti	Utl'	Uth	Uhl	Uhh	简要注释

#,PV2,2型光伏发电站，
参数组号	WECCMODEL	GRATEPOWER	SREF	B_BATTERY	SOC_max	SOC_min	SOC_ini	T_total	VLin	VLout	VHin	VHout	VL1	VL2	TL1	TL2	VH1	VH2	TH1	TH2	NLVRTFLG	LVRTPORTION	HVRTPORTION	TdlyVLin	TdlyVLout	TdlyVHin	TdlyVHout	PQ_flag	PQ_LHVRT_FLAG	IpCLL_LHVRT_norm_FLAG	Vq1	Iq1	Vq2	Iq2	Vq3	Iq3	Vq4	Iq4	Vp1	Ip1	Vp2	Ip2	Vp3	Ip3	Vp4	Ip4	Tfltr	Trp	Trf	Trv	Freq_flag	Krp	PPOI_flag	fdb1	fdb2	Dup	Ddn	Dup_Pmax	Ddn_Pmin	Perrmax	Perrmin	Kp_pp	Ki_pp	Ppoimax	Ppoimin	Tlag	Vcmp_flag	PFPOI_flag	QPOI_flag	Rc	Xc	Kc	Vpdb1	Vpdb2	Verrmax	Verrmin	Kp_pv	Ki_pv	Qpdb1	Qpdb2	Qerrmax	Qerrmin	Kp_pq	Ki_pq	Qpoimax	Qpoimin	Tft	Tfv	Pmax	Pmin	Qmax	Qmin	dPmax	dPmin	dQmax	dQmin	Ip_max	Ip_min	Iq_max	Iq_min	I_max	I_min	Tg	P_flag	Tpord	Kp_lp	Ki_lp	Tip	Qref_flag	V_flag	Q_flag	Tqord	Tiq	Kp_lqv	Ki_lqv	V_max	V_min	Kp_lv	Ki_lv	Kp_lq	Ki_lq	Vldb1	Vldb2	Kqv	Iqinjh	Iqinjl	LVRT_IN_PFLAG	KP_LVRT	Pset_LV	K1_Ip_LV	K2_Ip_LV	Ipset_LV	VZEROX	VBRKPT	IpBRKPT	LVRT_IN_QFLAG	KQ_LV	Qset_LV	K1_Iq_LV	K2_Iq_LV	Iqset_LV	Ip_LVREC0_FLAG	KIp_LVREC0	Ipset_LVREC0	TLVRT_RECOVER0	Iq_LVREC0_FLAG	KIq_LVREC0	Iqset_LVREC0	HVRT_IN_PFLAG	KP_HV	Pset_HV	K1_Ip_HV	K2_Ip_HV	Ipset_HV	HVRT_IN_QFLAG	KQ_HV	Qset_HV	K1_Iq_HV	K2_Iq_HV	Iqset_HV	Ip_HVREC0_FLAG	KIp_HVREC0	Ipset_HVREC0	THVRT_RECOVER0	Iq_HVREC0_FLAG	KIq_HVREC0	Iqset_HVREC0	LVRT_RECOVER_PFLAG	dIp_RECOVER_max	Tcons_Precover	Ip_rec_a	Ip_rec_b	Ip_rec_c	Ip_rec_d	Ip_rec_t0	LVRT_RECOVER_QFLAG	Tcons_Qrecover	ICONTYP_UBL	IK1_Ip_LV_UBL	IK2_Ip_LV_UBL	IIpset_LV_UBL	IK3_Ip_LV_UBL	IK1_Iq_LV_UBL	IK2_Iq_LV_UBL	IIqset_LV_UBL	IK3_Iq_LV_UBL	LVRT_flag	HVLT_flag	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	简要注释

#,BESS,1型储能电站（新版文件里没有）
参数组号	WECCMODEL	GRATEPOWER	SREF	B_BATTERY	SOC_max	SOC_min	SOC_ini	T_total	VLin	VLout	VHin	VHout	VL1	VL2	TL1	TL2	VH1	VH2	TH1	TH2	NLVRTFLG	LVRTPORTION	HVRTPORTION	TdlyVLin	TdlyVLout	TdlyVHin	TdlyVHout	PQ_flag	PQ_LHVRT_FLAG	IpCLL_LHVRT_norm_FLAG	Vq1	Iq1	Vq2	Iq2	Vq3	Iq3	Vq4	Iq4	Vp1	Ip1	Vp2	Ip2	Vp3	Ip3	Vp4	Ip4	Tfltr	Trp	Trf	Trv	Freq_flag	Krp	PPOI_flag	fdb1	fdb2	Dup	Ddn	Dup_Pmax	Ddn_Pmin	Perrmax	Perrmin	Kp_pp	Ki_pp	Ppoimax	Ppoimin	Tlag	Vcmp_flag	PFPOI_flag	QPOI_flag	Rc	Xc	Kc	Vpdb1	Vpdb2	Verrmax	Verrmin	Kp_pv	Ki_pv	Qpdb1	Qpdb2	Qerrmax	Qerrmin	Kp_pq	Ki_pq	Qpoimax	Qpoimin	Tft	Tfv	Pmax	Pmin	Qmax	Qmin	dPmax	dPmin	dQmax	dQmin	Ip_max	Ip_min	Iq_max	Iq_min	I_max	I_min	Tg	P_flag	Tpord	Kp_lp	Ki_lp	Tip	Qref_flag	V_flag	Q_flag	Tqord	Tiq	Kp_lqv	Ki_lqv	V_max	V_min	Kp_lv	Ki_lv	Kp_lq	Ki_lq	Vldb1	Vldb2	Kqv	Iqinjh	Iqinjl	LVRT_IN_PFLAG	KP_LVRT	Pset_LV	K1_Ip_LV	K2_Ip_LV	Ipset_LV	VZEROX	VBRKPT	IpBRKPT	LVRT_IN_QFLAG	KQ_LV	Qset_LV	K1_Iq_LV	K2_Iq_LV	Iqset_LV	Ip_LVREC0_FLAG	KIp_LVREC0	Ipset_LVREC0	TLVRT_RECOVER0	Iq_LVREC0_FLAG	KIq_LVREC0	Iqset_LVREC0	HVRT_IN_PFLAG	KP_HV	Pset_HV	K1_Ip_HV	K2_Ip_HV	Ipset_HV	HVRT_IN_QFLAG	KQ_HV	Qset_HV	K1_Iq_HV	K2_Iq_HV	Iqset_HV	Ip_HVREC0_FLAG	KIp_HVREC0	Ipset_HVREC0	THVRT_RECOVER0	Iq_HVREC0_FLAG	KIq_HVREC0	Iqset_HVREC0	LVRT_RECOVER_PFLAG	dIp_RECOVER_max	Tcons_Precover	Ip_rec_a	Ip_rec_b	Ip_rec_c	Ip_rec_d	Ip_rec_t0	LVRT_RECOVER_QFLAG	Tcons_Qrecover	ICONTYP_UBL	IK1_Ip_LV_UBL	IK2_Ip_LV_UBL	IIpset_LV_UBL	IK3_Ip_LV_UBL	IK1_Iq_LV_UBL	IK2_Iq_LV_UBL	IIqset_LV_UBL	IK3_Iq_LV_UBL	LVRT_flag	HVLT_flag	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	简要注释

#,MDCLN1,柔性直流输电直流线保护参数，59
参数组号	vpdcup	vpdclw	apdcup	tpdcup	apdcdf	tdcbrk	idcbk	tpdcdf	tpdvah	tpdval	Vvlih	Avlih	Tvlih1	Tvlih2	trest	Tretval	timres	Lkvsc	Tmsi	NIFILT1	CHI1	LMI1	RMI1	CLI1	LLI1	RLI1	NIFILT2	CHI2	LMI2	RMI2	CLI2	LLI2	RLI2	NJFILT1	CHJ1	LMJ1	RMJ1	CLJ1	LLJ1	RLJ1	NJFILT2	CHJ2	LMJ2	RMJ2	CLJ2	LLJ2	RLJ2	CI0	CJ0	SDIO	RDIO	ADIO	UDIO	STHY	RTHY	UTHY1	UTHY2	简要注释

#,STM,STATCOM参数，37
参数组号	SBASE	T1	T2	T3	T4	T5	Tp	Ts	Kp	Ki	Kd	Xt	Vmax	Vmin	ICMAX	ILMAX	Vstandby	Ks1	Ts7	Ts8	Ts9	Ap	Bp	Ts13	Ts14	Ts15	Ts16	Ks3	Vscsmax	Ierr	Ks2	Ts10	Ts11	Ts12	Vscsmin	简要注释

#,WDGEN1,双馈风力发电机参数，156
参数组号	GRATEPOWER	XPP	OMG_BASE	TJ_GEN	WTGMODEL	CONVERTYPE	TCO	NDBRflg	Ebst	Kdbr	NLVRTflg	VL1	VL2	TL1	TL2	LVRTP	VH1	VH2	TH1	TH2	HVRTP	NQMOD	TR	FN	TV	KPV	KIV	VERMN	VERMX	VFRZ	QMAX	QMIN	TC	TPWR	RC	XC	IPMAX	KQI	KVI	XIQMAX	XIQMIN	VMAX	VMIN	Npqflag	LphL	LqhL	ImaxTD	Iqmxv0	NLVPLflg	VZEROX	IPZEROX	VBRKPT	PBRKPT	RRPWR	LVPLDT	LVPLRRT	LVPLOSR	LVPLDDLY	LVPLUDLY	TVEMD	SWITCHIQK	SWITCHIIN	RHO	VWIND_CI	VWIND_CO	VWIND_RATE	VWIND0	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	ITURBINE_RADIUS	OMG_BASET	TJ_TURBINE	TUR_MODEL	AXIS_FLEX	AXIS_DAMP	TH	OMG_RATE	KPTRQ	KITRQ	TPC	Pmax	Pmin	DPmax	DPmin	Kpp	Kip	KPC	KIC	TP	THETAMAX	THETAMIN	DTHETAMAX	DTHETAMIN	NApcflg	Tw	TPAV	apcPa	apcPbc	apcPd	apcFa	apcFb	apcFc	apcFd	apcPmax	apcPmin	NWdinflg	KWI	dbwi	Tlpwi	Twowi	urlwi	drlwi	Pmxwi	Pmnwi	NQdroopflg	TLPQD	KQD	XQD	COSPHI	TRV	NWfflg	TMP1	TMP2	TMP3	TMP4	TMP5	TMP6	TMP7	TMP8	TMP9	TMP10	简要注释

#,WDGEN2,直驱风力发电机参数，156
参数组号	GRATEPOWER	XPP	OMG_BASE	TJ_GEN	WTGMODEL	CONVERTYPE	TCO	NDBRflg	Ebst	Kdbr	NLVRTflg	VL1	VL2	TL1	TL2	LVRTP	VH1	VH2	TH1	TH2	HVRTP	NQMOD	TR	FN	TV	KPV	KIV	VERMN	VERMX	VFRZ	QMAX	QMIN	TC	TPWR	RC	XC	IPMAX	KQI	KVI	XIQMAX	XIQMIN	VMAX	VMIN	Npqflag	LphL	LqhL	ImaxTD	Iqmxv0	NLVPLflg	VZEROX	IPZEROX	VBRKPT	PBRKPT	RRPWR	LVPLDT	LVPLRRT	LVPLOSR	LVPLDDLY	LVPLUDLY	TVEMD	SWITCHIQK	SWITCHIIN	RHO	VWIND_CI	VWIND_CO	VWIND_RATE	VWIND0	A1	A2	A3	A4	A5	A6	A7	A8	A9	A10	A11	A12	A13	A14	A15	A16	A17	A18	A19	A20	A21	A22	A23	A24	A25	ITURBINE_RADIUS	OMG_BASET	TJ_TURBINE	TUR_MODEL	AXIS_FLEX	AXIS_DAMP	TH	OMG_RATE	KPTRQ	KITRQ	TPC	Pmax	Pmin	DPmax	DPmin	Kpp	Kip	KPC	KIC	TP	THETAMAX	THETAMIN	DTHETAMAX	DTHETAMIN	NApcflg	Tw	TPAV	apcPa	apcPbc	apcPd	apcFa	apcFb	apcFc	apcFd	apcPmax	apcPmin	NWdinflg	KWI	dbwi	Tlpwi	Twowi	urlwi	drlwi	Pmxwi	Pmnwi	NQdroopflg	TLPQD	KQD	XQD	COSPHI	TRV	NWfflg	TMP1	TMP2	TMP3	TMP4	TMP5	TMP6	TMP7	TMP8	TMP9	TMP10	简要注释

#,SLM,配网综合负荷参数，36
参数组号	配网电阻	配网电抗	电动机类型	初始滑差	有功负载率	定子电阻	定子电抗	转子电阻	转子电抗	惯性时间	激磁电抗	机械力矩A	机械力矩B	功率因数	恒阻抗系数P_Z	恒阻抗系数Q_Z	恒电流系数P_I	恒电流系数Q_I	频率系数Fp	频率系数Fq	有无发电机	发电机初始有功	发电机初始无功	发电机额定容量	发电机额定有功	同步机模型	同步机参数组	励磁模型	励磁参数组	调速模型	调速参数组	pss模型	pss参数组	配网等值阻抗基准容量	简要注释
（iffifffffffffffffffffiffffiiiiiiiiis）


未对应的数据和表字段:
可控高抗参数，29
参数组号	电压量测环节时间常数	控制类型	Kp2	Ki2	Imax2	Imin2	Kp1	Ki1	Imax1	Imin1	K4	K3	Kf1	Tf1	K1	K2	Idmax	Idmin	Kf2	Tf2	死区	Vmax	Vmin	dltaT	dltaI	额定容量	X0	简要注释

直流线频率调制，20
参数组号	Td1	Tf1	E1	A1	B1	C1	D1	K1	Td2	Tf2	E2	A2	B2	C2	D2	K2	Pmax	Pmin	简要注释

直流线频率调制2型，12
参数组号	Trect	Krect	T1	DB1	Tinv	Kinv	T2	DB2	Pmax	Pmin	简要注释

直流线频率调制3型，24
参数组号	Tr1	Kr	DB1	K1	T1	DFmax1	DFmin1	INTmax1	INTmin1	Pmax1	Pmin1	Tr2	Ki	DB2	K2	T2	DFmax2	DFmin2	INTmax2	INTmin2	Pmax2	Pmin2	简要注释

UPFC并联侧模型，28
参数组号	Tv	Kiv	Vdimax	Vdimin	Kpv	Ipqmax	Ipqmin	Tish	Thsh	Tdv	Kidv	Vdcmax	Vdcmin	Kpdv	overvoltage	ovtime	undervoltage	uvtime	overfrequency	oftime	underfrequency	uftime	overcurrent	octime	oDCv	oDCvtime	简要注释

UPFC串联侧模型18
参数组号	Tp	Kip	Pdimax	Pdimin	Kpp	Tq	Kiq	Qdimax	Qdimin	Kpq	Vpqmax	Vpqmin	Tvpq	Thpq	overcurrent	octime	简要注释

6型LCC换流器 201
参数组号	DTLCC	RTHYR	VTHYOPN	VTHYCLO	DEG_FAIL	CRC	RRC	PLL_KP	PLL_KI	PCO_KP	TRACV	TRDCV	TRDCI	IBC_ON	ICMUNIT	TCMUNIT	Raovs	Tovs	Raovl	Tovl	Numovs	Tlimovs	Puprat	Plwrat	VSHIF_IR	TVDCS_IR	TVDCF_IR	TFTOS_IR	TSTOF_IR	VFTLM_IR	COMPK_IR	COMPU_IR	Ud_low	Ud_high	T_Ud_up	T_Ud_dn	Iomin_vdcl	Io_min	ICONTYP	Ts_CF_IN	G_CF_A	UK_CF_ABC	UK_CF_S	A_CF_MAX1	A_CF_MIN1	T_CF_HD1	T_CF_HD2	T_CF_PLS	T_CF_ON	T_CF_OFF	UACS_ACF	TUACS_ACF	TUACH_ACF	UACB_ACF	TUACB_ACF	TUACO_ACF	TUACA_ACF	UDCS_GM0	TUDCS_GM0	TUDCH_GM0	UDCB_GM0	TUDCB_GM0	IGAMATYP	A_comp	rf_T	DI_K	DI_T	ADIMAX	ADIMIN	AMAXUP	AMAXLW	ALPHA_SUB	ALPHALOW	T_slow	U1_RA	U2_RA	RAML1	RAML2	DECR	T1S_RA	T2S_RA	T1B_RA	T2B_RA	T1O_RA	T2O_RA	DU1_RA	Tfilt_U	Udcuplim	Udcdwlim	Uov_ref	Uov_TIN	Uov_TOU	Uov_DI	Uov_KP	Uov_KI	Vca_KP	Vca_KI	Vca_KP_UP	Vca_KP_LW	Vca_mgn1	Vca_mgn2	Vca_mgn3	ALPHE_RET	TH_RET1	TH_RET2	TH_RET3	ALPHE_RES	TH_RES1	TH_RES2	TH_RES3	TH_RESS	TH_RESSUC	TH_LVPRO	NFUL_RES	NDEP_RES	UDEP_RES	VK_RESSUC	VUPRT_RES	AUPRT_RES	ALIM_LOWV	DIord	Tfilt_I	GAINI	CCA_KP	CCA_KI	CCA_KP_UP	CCA_KP_LW	Ain1	Ain2	Ain3	Ain4	Ain5	Ain6	Aout1	Aout2	Aout3	Aout4	Aout5	Aout6	GCA_KP	GCA_KI	Th_Otc	TA_Otc	DAH_Otc	DAL_Otc	DVH_Otc	DVL_Otc	DEH_Otc	DEL_Otc	BRA_TH	BRA_MX	BRA_KP	BRA_KI	BRA_UP	BRA_LW	NCTRVORG	T_ADDGM	T_SUBGM	ADD_A_R_RAT1	ADD_A_R_LIM1	ADD_A_R_1	SUB_A_R_LIM1	SUB_A_R_LIM2	SUB_A_R_RAT1	SUB_A_R_RAT2	SUB_A_R_1	SUB_A_R_2	SUB_A_R_3	ADD_A_I_LIM1	ADD_A_I_LIM2	ADD_A_I_LIM3	ADD_A_I_1	ADD_A_I_2	SUB_A_I_LIM1	EMG_CONST	EMG_VOLT	ANGE_LOCK	TDY_LOCK	TSG_FAILU	TCT_FAILU	ORD_LOCK	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	Temp11	Temp12	Temp13	Temp14	Temp15	Temp16	Temp17	Temp18	简要注释

5型SVC 83
参数组号	GRATEPOWER	Trv	Tri	Trq	Vdb1	Vdb2	Tsr	Vdv	Ksl	Ki_vr	Kp_vr	dBmax_Ki	dBmin_Ki	Bmax	Bmin	Tsvc	Flag_Block	VL_Block	Tdly_LV_Block	VH_Block	Tdly_HV_Block	Flag_UV	VL_UV	Tdly_LV_UV	VH_UV	Tdly_HV_UV	Qcomp_UV	Flag_OV	VH_OV	Tdly_HV_OV	VL_OV	Tdly_LV_OV	Qcomp_OV	IFlag_POD_P	Tpod_P	TPw1	TPw2	TPs1	TPs2	TPs3	TPs4	Kpod_P	IFlag_POD_Ib	Tpod_Ib	TIbw1	TIbw2	TIbs1	TIbs2	TIbs3	TIbs4	Kpod_Ib	IFlag_POD_dV	Tpod_dV	TdVw1	TdVw2	TdVs1	TdVs2	TdVs3	TdVs4	Kpod_dV	IFlag_POD_f	Tpod_f	Tfw1	Tfw2	Tfs1	Tfs2	Tfs3	Tfs4	Kpod_f	Bpod_max	Bpod_min	Temp1	Temp2	Temp3	Temp4	Temp5	Temp6	Temp7	Temp8	Temp9	Temp10	简要注释

LFOD_VSC 16 
参数组号	Sitein	Ctype	Intype	Tr	Wadd	Kadd	Kp	Kri	Wc	Wo	Tup	Tlw	Outmax	Outmin	简要注释

差分方程负荷参数，13
参数组号	阶数	有功系数a1	有功系数a2	有功电压系数b0	有功电压系数b1	有功电压系数b2	无功系数a1p	无功系数a2p	无功电压系数b0p	无功电压系数b1p	无功电压系数b2p	简要注释
```



### **LF.Zone**  潮流计算分区信息

潮流计算分区信息。分区i4、所属区域编号i9、分区描述s。

### **LF.Area** 全国区域

全国区域。区域编号i9、区域描述s。

### **LF.L0_Method_2**  潮流作业定义（不起作用）

### **LF.L0_Method_1**  潮流作业定义（不起作用）

### **LF.PStation**  厂站信息

 厂站编号 、分区、第三列未知 、厂站名称。

### **LF.ML4** 柔性直流、换流站相关信息

一个文件中共有6张表

```
VSC#0
"版本号"

VSC#1
"直流母线",	"VSC换流站","LCC换流站","直流线路","DC/DC变换器的总数","交直流交替迭代方式"

VSC#2
"直流母线号", "直流母线类型"(1:正极母线;2:负极母线;3:接地点;4:阀连接点)，"接地方式"(0:不接地,1:接地)，"大地等效电阻",	"大地等效电感"，"接地引线电阻","接地引线电感"

VSC#3
"VSC换流站有效"(0无效;1有效)，"交流母线号"，"高压端直流母线号",	"低压端直流母线号",	"编号","交流侧基准电压","额定容量","Rc",	"Lc","电平数","子模块电容","损耗系数","VSC名称","极数","给定有功","给定无功","功率控制点标志",	"控制方式",	"给定电压幅值","给定电压相角","平衡站标志"(0非平衡站;1平衡站)，"连接方式","直流给定电压","滤波器容量","电流上限","调制比电压上限",	"调制比下限"

VSC#4
// 第 1 行
"LCC换流站有效"(0无效;1有效)，"交流母线号"，"高压端直流母线号",	"低压端直流母线号","编号","滤波器容量","所属换流器id","平抗","LCC名称",
// 第 2 行
"每极换流桥数",,"联结变压器单极总容量",	"铜损电阻值","漏抗值","交流侧额定线电压","阀侧出口额定线电压","初始抽头线电压",	"最高抽头线电压","最低抽头线电压","抽头级数","总零序电阻",	"总零序电抗"
// 第 3 行
"换流器类型"(0整流器;1逆变器)，"调节模式" (0定点燃角调变比;1定变比调点燃角)，"直流控制方式"(1定直流电流;2定直流功率;3定直流电压;4定点燃角)，"给定直流电流","给定直流功率","给定直流电压","点燃角/熄弧角初始值","点燃角/熄弧角最小值"

VSC#5
"有效标志" (0无效;1有效)，"i侧母线号","j侧母线号","编号","电阻",	"电感","电容","电流上限","额定电流","直流线路名称"

VSC#6
"DC/DC变换器有效" (0无效;1有效)，"R侧母线号","L侧母线号",	"编号","R侧控制功率"(MW，流入为正)，"电导","电阻","DC/DC元件名称"
```

### **LF.NL4 ** 普通直流相关信息

```
//第一行
是否投运i3、整流侧母线i6、逆变侧母线i6、线路编号i6、所属分区i6、线路说明s、

//第二行
整流侧接地引线电阻15/6、整流侧接地引线电感15/6、逆变侧接地引线电阻15/6、逆变侧接地引线电感15/6、直流线路电阻15/6、直流线路电感15/6、接地极整流侧电阻15/6、接地极逆变侧电阻15/6、单极整流侧平波电抗器电感15/6、单极逆变侧平波电抗器电感15/6、

//第三行
未知15/6

//第四行
整流侧换流变交流侧主抽头额定线电压15/6、整流侧换流变阀侧出口额定线电压15/6、整流侧每极换流桥数4i、整流侧换流变单极总容量15/6、整流侧换流变压器铜损电阻值15/6、整流侧换流变压器漏抗百分数15/6、整流侧换流变压器最高抽头线电压15/6、整流侧换流变压器最低抽头线电压15/6、整流侧换流变压器抽头级数15、整流侧换流变零序电阻15/6、整流侧换流变零序电抗15/6、

//第五行
逆变侧换流变交流侧主抽头额定线电压15/6、逆变侧换流变阀侧出口额定线电压15/6、逆变侧每极换流桥数4i、逆变侧换流变单极总容量15/6、逆变侧换流变压器铜损电阻值15/6、逆变侧换流变压器漏抗百分数15/6、逆变侧换流变压器最高抽头线电压15/6、逆变侧换流变压器最低抽头线电压15/6、逆变侧换流变压器抽头级数15、逆变侧换流变零序电阻15/6、逆变侧换流变零序电抗15/6、

//第六行
直流运行方式4i、整流侧换流变单极无功15/6、逆变侧换流变单极无功15/6、

//第七行
单极？？容量15/6、单极额定电压15/6、单极最小点燃角15/6、单极点燃角15/6、单极最小熄弧角15/6、单极熄弧角15/6、

//第八行
单极？？容量15/6、单极额定电压15/6、单极最小点燃角15/6、单极点燃角15/6、单极最小熄弧角15/6、单极熄弧角15/6
```



### **LF.Bus** 母线厂站关系

母线名称、基准电压、母线所属厂站的编号（LF.PStation 卡中第一列）、最高电压、最低电压、单相短路容量、三相短路容量。

### **LF.L0** 作业定义

潮流作业定义。（母线数、交流线路数、变压器绕组数、直流线路数、发电机数、负荷数、区域功率控制有效标记1、控制和UD功能1、未知、变电站数据有效标记、发电负荷比例因子标记、基准容量、电压上限标幺值、电压下限标幺值、允许计算误差、计算方法选择、最大迭代次数、区域功率控制有效标记2、控制和UD功能2、预设平衡点和读取上次潮流值标记（0为均不勾选；1为勾选读取上次潮流值；2为勾选预设平衡点；3为均勾选）、变电站数据有效标记2、未知、考虑变压器激磁阻抗标记、MATLAB接口有效标记、潮流作业编号、潮流作业名称）。

### **LF.L1** 母线（潮流计算必需）

母线名称、基准电压、所属分区、最高电压、最低电压、单相短路容量、三相短路容量。（母线编号为LF.L1卡的行号）

### **LF.L2** 交流线路（潮流计算必需）

投运状态、I侧母线（线路首端母线节点在LF.L1卡的行号）、J侧母线（线路末端母线节点在LF.L1表中的行号）、线路名称后的编号、正序电阻标幺值、正序电抗标幺值、正序电纳标幺值、所属分区、线路控制功能类型、控制参数组号、第十一列未知、第十二列未知、被控量的给定值、额定容量（kA）、容量上限百分比、被控结点名、被控元件编号、线路名称

### **LF.L3** 变压器/绕组（潮流计算必需）

投运状态、主变一侧母线节点在LF.L1卡的行号（三圈变行号前面多了“-”号以便区分三圈与两圈） 、另一侧母线节点在LF.L1卡的行号、主变各侧编号、正序电阻标幺值、正序电抗标幺值、各侧标准变比、激磁电阻、激磁电抗 、第十列未知、控制类型、控制元件组号、第十三列未知、第十四列未知、第十五列未知、被控量设定值、给定相角值、各侧额定容量、容量上限百分比、表内顺序编号、第二十一列未知、绕组类型、被控元件名、被控元件类型、主变绕组名称、第二十六列未知、各侧电压等级、最高档位1、最低档位1、主抽头档位1、电压步长1、第三十二列未知。

### **LF.L4** 直流线路

```
第1行
"有效标记","整流侧母线",	"逆变侧母线","线路编号","整流侧接地引线电阻(ohm)","整流侧接地引线电感(mH)","逆变侧接地引线电阻(ohm)","逆变侧接地引线电感(mH)","直流线路电阻(ohm)",	"直流线路电感(mH)","描述"

第2行
"接地极整流侧和逆变侧电阻(ohm)","第二行第二个字段",	"第二行第三个字段",	"单极整流侧和逆变侧平波电抗器电感(mH)"

第3行
"整流侧换流变交流侧主抽头额定线电压","整流侧换流变阀侧出口额定线电压","整流侧每极换流桥数",	"整流侧换流变接入补偿电容器滤波器单极容量(Mvar)","整流侧换流变单极总容量(Mvar)","整流侧换流变压器铜损电阻值","整流侧换流变压器漏抗值百分数","整流侧换流变压器最高抽头线电压","整流侧换流变压器最低抽头线电压","整流侧换流变压器抽头级数"

第4行
"逆变侧换流变交流侧主抽头额定线电压","逆变侧换流变阀侧出口额定线电压","逆变侧每极换流桥数",	"逆变侧换流变接入补偿电容器滤波器单极容量(Mvar)","逆变侧换流变单极总容量(Mvar)","逆变侧换流变压器铜损电阻值","逆变侧换流变压器漏抗值百分数","逆变侧换流变压器最高抽头线电压","逆变侧换流变压器最低抽头线电压","逆变侧换流变压器抽头级数"

第5行
"直流运行方式","单极运行电流","单极额定电压","单极最小点燃角","单极点燃角","单极最小熄弧角",	"单极熄弧角","分区编号"
```

### **LF.L5** 发电机（潮流计算必需）

投运状态、机组母线节点在LF.L1卡的行号、发电机类型、发电机有功功率标幺值、发电机无功功率标幺值、发电机母线电压标幺值、发电机母线电压相角、发电机无功上限标幺值、发电机无功下限标幺值、发电机有功上限标幺值、发电机有下限标幺值、控制参数组号、第十三列未知、第十四列未知、被控量给定值、第十六列未知、被控元件名、被控元件编号、发电机名称

### **LF.L6** 负荷（潮流计算必需）

投运状态、所挂母线节点编号、负荷编号、负荷类型、负荷有功功率标幺值、负荷无功功率标幺值、负荷母线电压标幺值、负荷母线电压相角、负荷无功上限标幺值、负荷无功下限标幺值、负荷有功上限标幺值、负荷有功下限标幺值、控制参数组号、负荷模型、负荷参数组号、被控量给定值、被控元件名、被控元件编号、负荷名称

### **LF.L7** 分区

 有效标记、分区编号、分区名称、第四列未知、第五列未知、第六列未知、第七列未知

### **LF.L10** 分区发电负荷

各分区发电负荷比例因子。有效标记、分区编号（LF.L7卡中的第二列）、电压等级标志（0为全部电压等级；其他数字为真实电压等级）、第四列未知、第五列未知、发电有功比例因子、发电无功比例因子、负荷有功比例因子、负荷无功比例因子。

### **LF.L20 **预设平衡点

有效标记、平衡点类型（1发电机，2负荷）、平衡点母线编号。

### **PHYBUS.LFI** 母线-母线编号

有效标识、母线名称、母线编号。



## 暂态卡

### **ST.S0** 暂态设置

（ST.S1表中母线总数、ST.S2交流线路总数、DEV.XFRM卡中所有主变的（包括换流站主变）绕组数（三圈变三个，两圈变一个）、ST.S4直流总个数、ST.S5发电机总行数、ST.S6负荷总个数、ST.S7静止无功补偿器个数、网络故障数量、有效节点扰动数量、第十列未知 、第十一列未知 、第十二列未知、 第十三列未知、计算总时间、积分步长、 第十六列未知、第十七列未知、第十八列未知、系统频率（0为50HZ，1为60HZ）、 第二十列未知、第二十一列未知、第二十二列未知、第二十三列未知、第二十四列未知、第二十五列未知、允许误差、第二十七列未知、作业名、第二十九列未知、滤波时间常数  ）。

- 可以在“暂态故障扫描”中设置ST.S0卡，具体操作步骤如下：

  - PSASP设置

    ![](D:\note\暂态ST.S0卡的设定1.png)

  - 暂态设置（在界面上修改某字段 在点击计算之后会同步修改ST.S0卡的对应字段）

    ```
    //开发注释：界面上显示数据的初始化过程在ZTransientTemplateDialog::ZTransientTemplateDialog构造函数。写ST.S0卡的过程在暂态计算准备计算文件的函数ZTransientFaultMemDb::generatePsaspSTFiles（1834行）
    ```

    ![](D:\note\暂态ST.S0卡的设定.png)

### **ST.S1** 母线 

母线名称及其行号。

### **ST.S2** 交流线路、电容器、电抗器、零序负荷

投运状态、线路首端母线节点在ST.S1表中的行号、线路末端母线节点在ST.S1表中的行号、线路名称后的编号、零序电阻标幺值、零序电抗标幺值、零序电纳标幺值、线路名称。

### **ST.S3** 变压器

 投运状态、主变一侧节点在ST.S1表中的行号、 主变另一侧节点在ST.S1表中的行号 （三圈变为何两侧均为中心点）、主变编号（三圈变各侧都有，两圈变只有一个）、正序电阻标幺值、正序电抗标幺值、各侧标准变比、第八列未知 、第九列未知 。

### **ST.S4 **直流线路相关参数

### **ST.NS4 **直流线路相关信息

ST.NS4 ——为直流线路相关信息。直流线路

```
//第一行
是否投运i6、整流侧母线i6、逆变侧母线i6、线路编号i6、未知i6、线路说明s、

//第二行
 1未知i6、2 i6、5型直流极1整流侧/1型直流整流侧调节器参数行号i6、0.000000未知15.6f、60.000000未知15.6f、5.000000未知15.6f、
 
//第三行
  2未知i6、5型直流极2整流侧/1型直流逆变侧电流调节器参数行号i6、      0.000000未知15.6f、2未知i6、5型直流极1逆变侧/1型直流逆变侧电压调节器参数行号i6、 0.000000未知15.6f、2未知i6、5型直流极2逆变侧/1型直流逆变侧息弧角调节器参数行号i6、0.000000未知15.6f、80.000000未知15.6f、15.000000未知15.6f、10.000000未知15.6f、
 
//第四行
    最低电压15.6f、最大电流值15.6f、最小电流值、再启动初始电流、再启动终了电流、      再启动初始段间隔、再启动过渡段间隔、欠电压保护动作电压、欠电压保护动作时间、
    
//第五行
10未知i6、0i6、0.000000未知、0.000000未知、0.000000未知、0.000000未知、0.000000未知、0.000000未知、0未知i6、0.000000未知。
```

 



### **ST.S5** 发电机组参数

（是否投运、发电机母线节点在ST.S1表中的行号、第三列未知、第四列未知、第五列未知、第六列未知、第七列未知、第八列未知、第九列未知、第十列未知、Xd’、Xd’’ 、X2、第十四列未知、额定容量（MVA）、额定功率（MW）、发电机名称）。

### **ST.S6** 负荷

（是否投运、负荷所挂母线节点在ST.S1表中的行号、负荷编号、负荷模型、负荷参数组号、恒定阻抗）。

### **ST.S7 **静止无功补偿器相关信息

ST.S7 ——静止无功补偿器相关信息。静止无功补偿器有效标记（0无效，1有效）、补偿器首端母线编号（L1卡）、补偿器末端母线编号（L1卡）、静补模型、参数组号、补偿器电抗、辅助信号1有效、辅助信号1类型、ass_par、ass_all_line、ass_linetype、辅助信号2有效、辅助信号2类型、描述。


### **ST.S11 **暂态网络故障生成卡

故障是否有效（0无效，1有效）、故障支路首端节点编号（ST.S1）、故障支路末端节点编号（ST.S1）、支路编号（ST.S2第四列）、故障点位置百分比、故障点新增母线（ST.S1）编号（通过设置故障点百分比会自动在ST.S1卡中添加一条母线同时ST.S0卡相应数值发生改变） 、 是否A相故障、是否B相故障 、是否C相故障、是否短路接地 、是否短路 、是否断线 、故障起始时间、故障结束时间、接入电阻、接入电抗。**每一行是一个故障卡。**

### **ST.S12 **节点扰动信息

有效标记、首端节点编号、末端节点编号、支路编号、节点扰动类型编号、判别类型、开始时间、结束时间、判别值、未知、延迟时间、未知。

- 可以在“暂态故障扫描”中设置节点扰动/切机卡，具体操作步骤如下：

  - 节点扰动

    ![](D:\note\ST.S12节点扰动卡.png)

  - 模板卡设置 与 实例卡生成

    ![](D:\note\ST.S12节点扰动卡2.png)

  - 在界面上配置模板卡，点击刷新按钮会出现有效的实例卡。有效切机卡的生成与安控设置相关。点击刷新之后需要选择预想故障分析结果文件。会根据结果文件生成实例卡。 

  - 对应的节点扰动信息会生成E文件 保存在\SmartPower\cfg\ZNodeDisturbance.etext中，其中只有切机表的数据是有效数据，可以写入ST.S12卡

  - 暂态计算的准备文件的时候正式将节点扰动信息写入ST.S12卡（**只有在PSASP设置中勾选“节点扰动信息”才会刷新ST.S12卡**）

    ```
    //开发注释：ST.S12的生成在ZTransientFaultMemDb::generatePsaspSTFiles（3253行）按照故障集 每个故障集故障设备不同，触发的机组不同，ST.S12卡不同
    ```

### **ST.S16 **串补相关信息。

ST.S16 ——串补相关信息。有效标记位i3、首段节点i6、末端节点i6、串补编号i6、串补模型号i6、串补参数组号（参照DATALIB）i6、未知i6、未知i6、未知i6、未知i6。

### **STCRIT **暂态计算稳定分析判据的相关设置

第一列、最大发电机功角差、最低母线电压、最低母线电压持续时间、最低发电机频率、最低发电机频率持续时间、 ？、？ 、功角峰峰值（度）、电压峰峰值（标幺）、？ 、？ 。

### **ST.SME **暂态计算输出信息

```
七类已解析的变量坐标（发电机功角、母线电压相角/频率、母线电压、发电机变量、直流线、交流线/变压器支路变量、负荷）

1、发电机功角——有效标记位、变量坐标的编号（1）、发电机编号（成对出现，如图1-2中的“已选项内容”，每一条记录包含两台机组，例如“川二滩#01_渝安稳82(deg.)”）、0、坐标名称。

2、母线电压相角/频率有效标记位、变量坐标的编号（12）、母线编号（成对出现，对应于图1-3中的已选项内容）、0、坐标名。

3、母线电压——**有效标记位、变量坐标的编号（2）、母线编号（已选项内容在ST.S1卡中的编号）、0、坐标名。（一行未满的用“0”补充）

4、发电机变量——有效标记位、变量坐标的编号（3）、发电机编号（所选的发电机在ST.S1卡中的编号）、发电机坐标变量的编号（编号对应于表1-1）、0、坐标名。

5、直流线——有效标记位、变量坐标的编号（6）、直流线首端母线编号（卡ST.S1）、直流线末端母线编号（卡ST.S1）、直流线编号（对应于图1-7所选的直流线在ST.S4中的编号）、直流线坐标变量的编号、0、坐标名称。

6、交流线/变压器支路变量——有效标记位、变量坐标的编号（7）、交流线首端母线编号（卡ST.S1）、交流线末端母线编号、交流支路编号（对应于图1-9所选的交流支路）、交流线坐标变量的编号、0、坐标名称。

7、负荷——有效标记位、变量坐标的编号（14）、负荷所挂母线编号（卡ST.S1）、负荷编号（所选的负荷在卡ST.S6中的编号）、负荷坐标变量的编号、0、坐标名称。

8、监视的坐标，其数据定义为：
有效标记位、变量坐标的编号、监视的坐标类型及其变量，用数字表示，每一个数据由三位数字组成，第一位为坐标类型，对应于备注1。后两位数字代表这个坐标在这一类坐标中的顺序，即在ST.SME文件中的这一类坐标中的顺序。若这一行未写完，则用“0”补全，每一行最多可写16个坐标数据（例如102，代表监视的是发电机功角类型，而且是ST.SME文件里发电机功角这一类中的排第2的坐标）、0、“”。

9、最后一行固定为：1,11,     3,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,     0,'',

10、编号为99的代表上一行坐标内容未完。

六类未解析的变量坐标：
感应电动机变量（4）；
SVC/CSR/STATCON变量（5）；
固定/可控串补变量（13）；
多端直流/直流电网变量——VSS换流器（15）；
多端直流/直流电网变量——直流线（16）；
多端直流/直流电网变量——LCC换流器（18）；
```

- 可以在“暂态故障扫描”中设置输出信息，具体操作步骤如下：
  - 输出选择![](D:\note\ST.SME输出信息.png)
  - 在输出信息选择界面上对输出信息进行修改（如果smartpower/data目录下有ST.SME，该界面读取文件夹下的信息，否则显示原文件模型中SME文件的内容）
  - 在暂态计算准备文件的过程中，如果smartpower/data/SME文件夹下有ST.SME则读取文件夹下的信息，如果没有则使用源文件模型中SME文件的内容进行计算

### **ST.MS4 **多端直流电网VSC换流器相关信息

（有效标记i3、首端母线编号i6、末端母线编号i6、换流器编号i6、模型i6、？i6）

### **ST.LS4  **多端直流线路相关信息

（有效标记、首端母线编号、末端母线编号、？、？、？）

### **ST.MLCC **多端直流相关信息

ST.MLCC ——多端直流LCC换流器相关信息。LCC换流站有效标记(0无效;1有效)i2、交流母线号i6、高压端直流母线号i6、低压端直流母线号i6、LCC换流器编号i6、未知i6、未知i6。

 ### **ST.SCDATE **短路计算计算条件选择设置

（是否考虑电压系数C、是否不考虑并联电容器、是否不考虑并联电抗器、是否忽略支路电阻、是否忽略变压器非标准变化、是否不考虑交流线对地电容、是否不考虑串联电容器、是否考虑负荷、是否选PSASP基本计算方法、是否考虑继电保护整定规则条件、是否考虑国家短路计算标准条件、电压系数C的值、？、？、计算开断电流时间、？、？、？、是否考虑负荷为恒阻抗、是否只考虑负荷中的感应电动机部分）。

### **ST.SCC **短路计算计算功能设置卡

（短路计算为0/戴维南等值计算为1、基于方案为0/基于潮流为非零39为潮流文件编号、简单故障为0/复杂故障为1、故障类型（三相短路为1；单相接地为2；两相短路为3；两相接地短路为4）、？、？、？、是否快速扫描即只计算故障点短路电流（是为1否为0）、是否计算直流多馈入短路比（是为1否为0））。

 

## 潮流计算结果文件解析

### **LF.CAL **         

### **LF.LP1** 母线（暂态计算必需）

潮流计算后母线电压标幺值、母线电压相角、母线名称。

### **LF.P1D **

潮流计算后母线电压标幺值、母线电压相角。

### **LF.LP2 **交流线路（暂态计算必需）

首端节点编号、交流线路首端节点编号、线路编号、首端有功标幺值、首端无功标幺值、末端无功标幺值、末端无功标幺值、始端充电功率、末端充电功率、线路名称。

### **LF.LP3 **主变（暂态计算必需）

主变一侧母线节点在ST.S1表中的行号、另一侧母线节点在ST.S1表中的行号、主变各侧编号、绕组首端有功标幺值、绕组首端无功标幺值、绕组末端有功标幺值、绕组末端无功标幺值、第八列未知、第九列未知、主变绕组名称。



### **LF.LP4** 双端直流线路

第1行

直流首端母线节点编号，直流末端母线节点编号，直流线路编号，

第2行

第3行

第4行

第5行

第6行

### **LF.LP5 **发电机（暂态计算必需）

母线编号、有功出力、无功出力、未知、发电机名称。

### **LF.LP6 **负荷（暂态计算必需）

所挂母线编号、负荷编号、负荷有功、负荷无功、负荷名称。

### **LF.UDP **潮流计算用户自定义信息。

### **LFERR.LIS ** 潮流计算过程错误信息。

### **lfreport.lis **潮流计算迭代过程及平衡机

潮流计算迭代过程及平衡机上有功功率、无功功率

### **slack.lis **平衡机

节点名称及其有功功率、无功功率

 

## 暂态计算结果文件解析

### **ST.UDP **用户自定义模型计算结果。

### **STCONV **机组

时间、迭代次数、最大偏差母线 、偏差。

### **STERR.LIS **暂态计算过程中的错误和警告信息。

### **STOUT **输出信息的变量坐标。

### **ST.CAL**

### **STANA**

### **STACTION **

### ***.sot ** 监视坐标信息的报表

SOT文件的生成过程在每个故障组暂态计算结束之后，并且在“PSASP设置”中勾选“生成SOT文件"

**生成SOT文件必须要有SME文件和暂态计算的结果.FN文件**



## 未知卡信息

### **DEV.SECTIONDEV **

### **NAME **

 