## 项目注意事项

### 1.关于新项目新界面添加到已有工程中

此时应修改已有工程的.pro文件，在对应的INCLUDEPATH或SOURCE中添加新的路径。

### 2.关于QT的编码规范

所有QString定义的变量， 不论中文英文，都要用QStringLiteral来转换。要不然使用编译检查的时候会出错，为了流畅的升级到Qt5.9，定义以下规范：

```c++
比如 头文件 zlocalcodec.h
QString str = QStringLiteral("确定");
QString str = QStringLiteral("ok");  //即使是英文也要用QStringLiteral转换。
QString str = QStringLiteral("%1%2").arg(text).arg(text2);
QString str = str.replace(QStringLiteral(">"), QStringLiteral(""));
QStringList list = str.split(QStringLiteral(","));
```



QString与ZString转换的方式如下：
QString转ZString，使用toZString(),头文件是qtconverters.h 
**ZString转QString，使用toQString()**:
示例：

```C++
QString str = zStr.c_str(); //错误的写法
QString str = toQString(zStr); //正确的写法
ZString zStr = toZString(qStr); //正确的写法
```

### 3.关于QString的判空

```
QString str;
str.isEmpty();//返回一个bool值，如果字符串为空返回true，否则返回false
```

### 4.编译问题集锦

graphwidget编译不过 先按照如下顺序编译lib_report>>lib_smart_ui>>graphwidget（graphwidget对lib_smart_ui有依赖，lib_smart_ui对lib_report有依赖）

### 5.调试内存泄漏问题

```
#if defined(_DEBUG) && defined(_USE_MFC_) 
#include <afxwin.h>         // MFC core and standard components
#endif


#if defined(_DEBUG) && defined(_USE_MFC_)
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
```

- 1运行refreshconfig_xxxx.bat
- 2 在项目配置里加上_USE_MFC_
- 3 编译通过之后运行程序
- 4 关闭程序后查看输出框



## 3.0使用笔记

#### 1.将2.0的参数库迁移到3.0

- 运行zautomigrate，选中要迁移的参数库。确定之后参数库就更新好啦。

- 2.0的库和3.0的库主要区别

  是表中关联的字段都是uuid了。比如2.0厂站表里owner，就直接是owner表里的名称。3.0里是owner表里的uuid。这样当owner的名称变化的时候，厂站表不需要去维护。



#### 2.修改smartdb的配置项（对应界面上“配置”-“环境配置”-“数据”）

- 在smartdb.template.etext里面添加字段

- 使用zuserconfig -c 生成代码（zconfigcontentsmartdb.h zconfigcontentsmartdb.cpp）
- 注意 枚举不可以使用常量定义



#### 3.新增参数库枚举

- 3.0
  - src_intel/zautodefine/file/define.etext 中添加新的枚举
  - 运行zautodefine.exe
  - 代码生成在zautodefine/lib_db 和 lib_dbio底下
- 2.0
  - /src_smart/zdbdef/define.etext 
  - zdbdef.exe
  - 代码生成在所需的位置 不需要替换





## CPLEX使用经验

#### 1.使用前检查是否已有cplex在运行

#### 2.当前某次计算时间过长时，可以检查日志文件（cplex.log)是否异常

- 日志文件大小超限的话可以考虑删除

