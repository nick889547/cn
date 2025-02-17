# 从云主机 MySQL 迁移到云数据库 MySQL
本文主要讲述如何从云主机自建 MySQL 迁移到京东云云数据库 MySQL。从云主机自建数据库迁移至云数据库后，业务可减轻运维压力，仅需关注运维使用即可。

## 注意事项
* 新建的 MySQL 实例需要和云主机在同一个 **私有网络** 内。
* 新建的 MySQL 实例的容量空间要确保不能小于在云主机中自建的 MySQL 。

## 操作步骤
1. 创建云数据库 MySQL，具体的创建步骤请参考 [创建云数据库 MySQL 实例](../../../Operation-Guide/Instance/Create-Instance.md)。
2. 通过控制台进行库的创建，需确保云主机自建的 MySQL 中需要导出的库名在云数据库 MySQL 中同样的创建了一遍，具体的创建步骤请参考 [创建库](../../../Operation-Guide/Database-Management/Create-Database.md)。
3. 通过控制台进行数据库账号的创建，也可以使用创建云数据库 MySQL 的时候的账号，然后赋予这个账号在第 2 步操作中新建的库的 **读写** 权限，具体的创建步骤请参考 [创建账号](../../../Operation-Guide/Account/Create-Account/MySQL-Create-Account.md)。
4. 完成云数据库 MySQL 创建和初始化工作之后，开始从云主机中自建的 MySQL 进行数据导出到云主机本地的操作，执行命令
   ```SQL
    mysqldump -u用户名 -p密码 --single-transaction --set-gtid-purged=OFF -B 数据库名称 > /路径/导出文件名.sql
    ```
    **参数描述**<br>
      用户名：自建数据库的用户名。<br>
      密码：自建数据库的密码。<br>
      数据库名称：填写您需要导出的库名，多个库名通过空格来分隔。<br>

5. 完成云主机中自建的 MySQL 数据导出到本地之后，就可以将数据导入到云数据库 MySQL 中，执行命令

    ```SQL
    mysql -u用户名 -p密码 -h 云数据库域名 < /云主机路径/导出文件名.sql
    ```
    **参数描述**<br>
      用户名：第 3 步操作中的用户名。<br>
      密码：第 3 步操作中的用户对应的密码。<br>
      数据库域名：云数据库 MySQL 的域名可以在实例的详情页查看。<br>
    
6. 如果没有任何错误提示，表示导入成功。登录数据库检查数据导入是否有缺失。
