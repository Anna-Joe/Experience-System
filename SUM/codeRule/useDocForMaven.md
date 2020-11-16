#### maven引入本地包 用于打包
1、导入jar包至maven仓库
//南瑞接口包
mvn install:install-file -Dfile=D:\cimpower_web\src\jar\FIDBAccessModel.jar -DgroupId=com.wrpower -DartifactId=FIDBAccessModel -Dversion=1.0 -Dpackaging=jar

mvn install:install-file -Dfile=D:\cimpower_php\java\jar\FIDBAccessV2For1.6.jar -DgroupId=com.wrpower -DartifactId=FIDBAccessV2For1.6 -Dversion=1.0 -Dpackaging=jar

mvn install:install-file -Dfile=D:\cimpower_php\java\jar\NDBAccessModel.jar -DgroupId=com.wrpower -DartifactId=NDBAccessModel -Dversion=1.0 -Dpackaging=jar

mvn install:install-file -Dfile=D:\cimpower_php\java\jar\NDBAccessV2For1.6ForFuture.jar -DgroupId=com.wrpower -DartifactId=NDBAccessV2For1.6ForFuture -Dversion=1.0 -Dpackaging=jar


//达梦数据库包
mvn install:install-file -Dfile=D:\cimpower_php\java\package\gbase_jar\jdbc\Dm7JdbcDriver17.jar -DgroupId=com.dm -DartifactId=Dm7JdbcDriver17 -Dpackaging=jar -Dversion=1.7.0


mvn install:install-file -Dfile=D:\cimpower_php\java\package\gbase_jar\jdbc\dialect\DmDialect-for-hibernate4.0.jar -DgroupId=com.dm -DartifactId=hibernate4 -Dpackaging=jar -Dversion=4.0

//国调权限包
mvn install:install-file -Dfile=D:\cimpower_php\java\package\zeus-inner-api-1.10.5.jar -DgroupId=com.wrpower -DartifactId=zeus-inner-api -Dpackaging=jar -Dversion=1.10.5

mvn install:install-file -Dfile=D:\cimpower_php\java\package\dcloud.common.auth-4.0.jar -DgroupId=com.wrpower -DartifactId=dcloud.common.auth -Dpackaging=jar -Dversion=4.0



3、打开控制台 运行maven命令

mvn install:install-file  

-Dfile=jar文件所在路径（这里使用绝对路径） 

-DgroupId=包名

-DartifactId=项目名  

-Dversion=版本号  

-Dpackaging=jar 

2、配置pom.xml，将maven仓库中的包使用
        <dependency>
            <groupId>com.wrpower</groupId>
            <artifactId>FIDBAccessModel</artifactId>
            <version>1.0</version>
        </dependency>

        <dependency>
            <groupId>com.wrpower</groupId>
            <artifactId>FIDBAccessV2For1.6</artifactId>
            <version>1.0</version>
        </dependency>
    
        <dependency>
            <groupId>com.wrpower</groupId>
            <artifactId>NDBAccessModel</artifactId>
            <version>1.0</version>
        </dependency>
    
        <dependency>
            <groupId>com.wrpower</groupId>
            <artifactId>NDBAccessV2For1.6ForFuture</artifactId>
            <version>1.0</version>
        </dependency>


​		
添加依赖后，代码没问题情况下。
点击Maven的install即可 会在maven仓库文件夹中生成jar包。

查看maven编译程序所依赖的classpath
mvn compile -X -e
在输出信息中 查找"javac"