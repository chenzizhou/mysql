# mysql
1）环境变量中新增（新增在path中）:  D:\program\mysql\mysql-8.0.21-winx64\bin
2）在mysql-8.0.21-winx64文件下创建my.ini  注意：不用在此目录下创建data文件（后期会自动创建）
3）在my.ini文件中填写如下内容（注意：路径根据自己的实际路径调整，同时一定是“\\”不是“\”，其他内容不变）：

[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8
[mysqld]
#设置3306端口
port = 3306
# 设置mysql的安装目录
basedir=D:\\program\\mysql\\mysql-8.0.21-winx64
# 设置mysql数据库的数据的存放目录
datadir=D:\\program\\mysql\\mysql-8.0.21-winx64\\data
# 允许最大连接数
max_connections=200
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB

4）使用管理员运行cmd，并进入你刚解压下来的目录的bin文件夹
5）依次运行在管理员cmd中运行以下命令
mysqld --initialize-insecure --user=mysql --console
mysqld -install (如报Install/Remove of the Service Denied! 则为非管理员运行)
net start mysql（如果报错显示MySQL 服务无法启动则回到my.ini文件，修改文件夹目录那里一定是"\\"，同时不要修改端口，使用3306即可）
6）新启cmd 执行 `mysql -u root -p`  因无密码 直接回车即可
7）ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';
8）flush privileges;  --重新加载权限表
