## 杭州局风险评估微服务

### 1.基态模型 web_server_basemodel 

- 输入 

  - 检修文件
  - 基本文件路径

- 输出

  - 生成回滚的基态文件

  - 成功与否

- 待办：

  - 微服务配置 cfg，log，port
  - baseModelService：get方法， 调用weeklyMaintProcess，返回结果
  - 使用postman测试
  - 跟java端互传消息

### 2.备自投自动生成 web_server_bztauto

- 输入 
  - 厂站uuid
  - 自动读取基态文件
- 输出
  - 调用备自投转化函数 生成转换后的备自投
  - 返回固定格式的json（参考ZBztCalcService）
- 待办：
  - 微服务配置 cfg，log，port
  - 备自投转换函数 移动到lib_smart_common 现在在zsystemhelper里面
  - bztAutoService：post方法， 调用weeklyMaintProcess，写一个生成json的函数，返回结果
  - 获取厂站uuid的json作为body，使用postman测试
  - 跟java端互传消息

### 3.风险报表 web_server_monthreport(仅修改)

- 输入
  - 计算id
  - 文件路径（包含基态文件，备自投文件，检修文件）
  
- 输出
  - 七天的检修风险报表
  - 根据报表返回固定格式的json（参考现有风险报表格式）
  
- 待办：
  
  - 结果表里缺的数据：
    - 检修设备的id
    - 检修组id
    - 检修组名称
  - 分为已匹配的风险和未匹配的风险
    - 风险匹配的逻辑是通过预想故障的停电厂站和检修设备之间的拓扑关系（有则为匹配上的风险）
    - 没有则为未匹配的风险
  
  - 根据最终的风险报表生成json文件
  - 修改数据库的字段 修改riskcaldata

### 4.先把C服务全部做完再考虑java的问题