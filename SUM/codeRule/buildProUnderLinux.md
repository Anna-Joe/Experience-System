### 1.备份

​	tar -cvf _src.tar.gz ./src



### 2.覆盖src中的代码

逐个代码文件夹复制粘贴

**注意lib_bizmemdb.pro里web相关的宏**

### 3.编译代码

#### 逐个编译（容易发现错误

cd $CIMPOWERROOT/src/src_self/planning&&zrmake    
cd $CIMPOWERROOT/src/src_self/zadapters&&zrmake&&     
cd $CIMPOWERROOT/src/src_lib/auxlib&&zrmake&&    
cd $CIMPOWERROOT/src/src_cim/cimxml&&zrmake&&    
cd $CIMPOWERROOT/src/src_lib/lib_smart_common&&zrmake&&    
cd $CIMPOWERROOT/src/src_lib/lib_smart_config&&zrmake&&    
cd $CIMPOWERROOT/src/src_intel/lib_db&&zrmake&&   
cd $CIMPOWERROOT/src/src_intel/lib_bizmemdb&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/cpprestlib&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/dmsLoopSearch&&zrmake    

#### 批量编译（基本不会编译出错的项目

cd $CIMPOWERROOT/src/src_web/web_server_maintplanparse&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_monthreport&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_file&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_server_bztcalc&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_riskcalc&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_verificationcalc&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_risk_ca&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_sense&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_translimit&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_risk_customizetranslimit&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_maintplanparse&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_monthreport&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_bztcalc&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_risk_verification&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_netrefactor_calc&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_netrefactor_settings&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_netrefactor_graphic&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_netrefactorcalc&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_netrefactorsettings&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_server_emsload&&zrmake&&       
cd $CIMPOWERROOT/src/src_web/web_emsload_import&&zrmake&&      
cd $CIMPOWERROOT/src/src_web/web_dmsDataCatcher&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_rjys_writebpa&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_rjyswriteBpa&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_risk_bztauto&&zrmake&&     
cd $CIMPOWERROOT/src/src_web/web_server_bztauto&&zrmake&&      
cd $CIMPOWERROOT/src/src_web/web_server_basemodel&&zrmake&&   
cd $CIMPOWERROOT/src/src_web/web_paramcompare_diff&&zrmake&&      
cd $CIMPOWERROOT/src/src_web/web_paramcompare_mapper&&zrmake&&        
cd $CIMPOWERROOT/src/src_web/web_paramcompare_rewriteBpa&&zrmake&&     
cd $CIMPOWERROOT/src/src_web/web_paramcompare_parseCime&&zrmake&&    
cd $CIMPOWERROOT/src/src_web/web_server_paramcompare&&zrmake     



//这三个暂时不用编译
//cd $CIMPOWERROOT/src/src_web/web_server_ca&&zrmake&&
//cd $CIMPOWERROOT/src/src_web/web_server_sense&&zrmake&&
//cd $CIMPOWERROOT/src/src_web/web_server_translimit&&zrmake&&

#### 当前目录下编译

zmake zrmake



### 4.关闭服务

#### 查看进程id

ps -ef|grep web

#### 杀死进程（通过id

kill id

#### 杀死进程（批量

pkill -9 web（杀死所有以web开头的服务



### 5.清空共享内存

#### 查看共享内存

ipcs -m

#### 清理共享内存

ipcrm -M 0x6504001c;ipcrm -M 0xff050022;ipcrm -M 0x6c05002e;ipcrm -M 0xb6050032;ipcrm -M 0xf4050033;ipcrm -M 0x25050035;ipcrm -M 0x77050037;

#### 清空所有

ipcrm -a



### 6.复制编译后的可执行程序路径

cp  /home/zjuadmin/cimpower/release/bin/*  /home/zjuadmin/cimpower/bin      
cp  /home/zjuadmin/cimpower/release/lib/*   /home/zjuadmin/cimpower/lib   



### 7.启动服务

(nohup web_server_file&)&&   
(nohup web_server_maintplanparse&)&&   
(nohup web_server_monthreport&)&&   
(nohup web_server_riskcalc&)&&   
(nohup web_server_bztcalc&)&&   
(nohup web_server_netrefactorcalc&)&&   
(nohup web_server_netrefactorsettings&)&&   
(nohup web_server_emsload&)&&   
(nohup web_server_verificationcalc&)&&   
(nohup web_dmsDataCatcher&)&&   
(nohup web_rjys_writebpa&)&&   
(nohup web_server_bpaparse&)&&    
(nohup web_server_basemodel&)&&      
(nohup web_server_bztauto&)&&      
(nohup web_server_paramcompare&)    


(nohup web_server_ca&)&&
(nohup web_server_sense&)&&
(nohup web_server_translimit&)&&
