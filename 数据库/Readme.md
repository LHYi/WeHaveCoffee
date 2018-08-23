# VS  ASP.NET Web应用程序后台连接SQL Server数据库教程

打开服务资源管理器>>数据连接>>添加连接

![1535036563017](C:\Users\Yang\AppData\Local\Temp\1535036563017.png)

选择数据源>服务器名输入"  .  "为本机>选择或输入数据库名称or附加数据库文件

![1535041843178](C:\Users\Yang\AppData\Local\Temp\1535041843178.png)

测试连接>>确定

![1535041941264](C:\Users\Yang\AppData\Local\Temp\1535041941264.png)

可以看到数据库已经导入

![1535041996836](C:\Users\Yang\AppData\Local\Temp\1535041996836.png)

导入成功后，为了在数据访问层简便操作SQL Server数据库，这里使用Entity Framework

  首先在模型层Models类库上右键>>管理NuGget程序包

![1535042300886](C:\Users\Yang\AppData\Local\Temp\1535042300886.png)

在浏览中找到安装EntityFramework

![1535042479160](C:\Users\Yang\AppData\Local\Temp\1535042479160.png)

**Models安装EF后，对数据访问层DAL以及业务逻辑层BLL进行相同操作，都安装上EF**



全都安装完成后，在Models类库上右键>>添加>>新建项

![1535042675058](C:\Users\Yang\AppData\Local\Temp\1535042675058.png)

添加一个实体数据模型并命名

![1535042795242](C:\Users\Yang\AppData\Local\Temp\1535042795242.png)

这里用的是DBfirst，选择来自数据库的EF设计器

![1535042849416](C:\Users\Yang\AppData\Local\Temp\1535042849416.png)

新建连接选择自己的数据库

![1535042966615](C:\Users\Yang\AppData\Local\Temp\1535042966615.png)

操作与最初连接数据库相同

![1535043017378](C:\Users\Yang\AppData\Local\Temp\1535043017378.png)
勾选  “表”

![1535043217648](C:\Users\Yang\AppData\Local\Temp\1535043217648.png)

选择 “ 全是 ”

、![1535043317729](C:\Users\Yang\AppData\Local\Temp\1535043317729.png)

打开Models\引用\App.config

找到图中第18行，复制

![1535043501214](C:\Users\Yang\AppData\Local\Temp\1535043501214.png)

打开WebSite \ Web.config

找到两个<connectionStrings>，也就是下图11、13行，在12、13行之间**粘贴**。

![1535043546374](C:\Users\Yang\AppData\Local\Temp\1535043546374.png)



  然后就大功告成了！可以在数据访问层或业务逻辑层对数据库进行增删改查等操作，具体操作方法语言自行搜素EF教程。





## 常见问题及解决方案

### SQL Server如何导入.mdf .ldf 文件

方法：https://jingyan.baidu.com/article/09ea3ede21258cc0afde3943.html

### 连接到数据库时出错

![1535043139361](C:\Users\Yang\AppData\Local\Temp\1535043139361.png)

打开SQL Server配置管理器，将SQL Server（MSSQLSERVER）启动或重新启动

![1535043915648](C:\Users\Yang\AppData\Local\Temp\1535043915648.png)

### 连接数据库时打开.mdf提示无法打开，文件正在使用

打开SQL Server配置管理器，将SQL Server（MSSQLSERVER）停止即可

![1535044076398](C:\Users\Yang\AppData\Local\Temp\1535044076398.png)



### 连接数据库时打开.mdf提示拒绝访问

解决方法：https://jingyan.baidu.com/article/e2284b2b456c93e2e7118d7b.html