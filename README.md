# distributed
基于分布式的机票架构网站

机票订购分布式架构网站，包括各个角色的前端（网页Web端）和后端（JAVA服务器端） 包括：1.机票代理商2.银行3.主网站 1.机票代理商 向主网站提供机票订购服务。自己本身具有管理界面可以进行机票的添加/修改/删除/查询，可以进行订单的查询 2.银行 向主网站提供购买时的支付服务/银行账号的登录与注册。自己本身具有查看用户账户列表/用户订单列表的功能 3.主网站 主网站就是用户使用的网站，用户可以进行注册和登录，用户登录后可以按代理商/价格/日期对机票进行筛选与购买（支付时需要登录银行账户如果没有则需进行注册），同时可以查看自己的订单。

数据库： 云数据库MySQL 部署： Tomcat 云服务器（如需部署至公网） 开发环境： JetBrains WebStorm 2018.1.3 x64 IntelliJ IDEA 2018.1.4 x64 MySQL Workbench 6.3 CE Angular CLI

前端：Angular 6.0.1 , PrimeNg 6.0.0 , bootstrap 4.1.1 后端：Spring boot , Spring cloud , Spring JPA , Spring cloud eureka , Spring Feign Remote 数据库：MySQL 5.7 前端界面采用PrimeNg和bootstrap框架，使界面更美观。前端逻辑采用Angular6.0.1，通过Router进行页面跳转，通过service进行前端用户登录信息的存储，前端与后端完全分离，仅进行数据交互。通过Angular框架封装的HttpClient与后端Spring MVC进行json格式的数据交互，传递对象以及对象集合。后端使用Spring Cloud EurekaServer作为服务注册中心，代理商以及银行通过Spring Cloud EurekaClient在服务注册中心提供服务，主网站通过Spring Feign Remote调用代理商以及银行在服务注册中心提供的服务。
