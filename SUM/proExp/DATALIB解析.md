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



