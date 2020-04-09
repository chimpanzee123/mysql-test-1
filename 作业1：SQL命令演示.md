从零开始学习MySQL语言命令
一、介绍对数据库操作相关的命令
1.创建一个新的数据库
执行命令如下:
```SQL
create database test1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/1.png?raw=true)
2.查看和选择数据库：
执行命令如下：
```SQL
show databases;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/2.png?raw=true)
3.删除数据库：
执行命令如下：```SQL
drop database test1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/3.png?raw=true)
二、如何查看MySQL数据库中的存储引擎
1.查看所支持的存储引擎
执行命令如下:
```SQL
show engines;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/4.png?raw=true)
2.查看默认的存储引擎
执行命令如下:
```SQL
show variables like'%storage_engine%'
;```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/5.png?raw=true)
三、介绍对表操作的相关命令
1.在数据库中创建一个新的表
执行命令如下:
```SQL
create table t_dept(
deptno int,
dname varchar(20),
loc varchar(40)
);
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/6.png?raw=true)
2.查看表的定义信息
执行命令如下:
```SQL
desc t_dept;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/7.png?raw=true)
3.删除表
执行命令如下:
```SQL
drop table t_dept;
desc t_dept;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/8.png?raw=true)
4.修改表名
执行命令如下:
```SQL
alter table t_dept1 rename t_dept9;
desc t_dept9;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/26.png?raw=true)
5.增加字段和删除字段
执行命令如下:
```SQL
alter table t_dept1 add fname char(20);
desc t_dept1;
```
在表的最后面增加字段
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/25.png?raw=true)
执行命令如下:
```SQL
alter table t_dept1 add bname char(10) first;
desc t_dept1;
```
在表的最前面增加字段
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/17.png?raw=true)
执行命令如下:
```SQL
alter table t_dept1 add snake char(10) after ename;
desc t_dept1;
```
在表指定字段后增加字段
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/18.png?raw=true)
执行命令如下:
删除字段
```SQL
alter table t_dept9 drop gname;
desc t_dept9;
```

6.修改字段
修改字段的数据类型
执行命令如下:
```SQL
alter table t_dept1 modify bname varchar(10);
desc t_dept1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/20.png?raw=true)
同时修改字段的名字和数据类型
执行命令如下:
```SQL
alter table t_dept9 change fname gname char(10);
desc t_dept9;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/27.png?raw=true)
修改字段的顺序
执行命令如下:
```SQL
alter table t_dept9 modify gname char(10) after bname;
desc t_dept9;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/28.png?raw=true)
四、操作表的约束
执行命令如下:
```SQL
create table t_dept2(
deptno int not null,
dname varchar(20) default 'petter',
cname varchar(20) unique,
loc varchar(40),
number int primary key auto_increment
);
desc t_dept2;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/13.png?raw=true)
五、数据的操作
1.插入数据记录
执行命令如下:
```SQL
insert into t_dept1 values('haohao','jack','linfen',123,4587);
select*from t_dept1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/14.png?raw=true)
2.同时插入多条数据记录
执行命令如下:
```SQL
insert into t_dept1 values(
'xiaofang','mary','kashi',123,4819),
('shuaiqi','king','italy',123,4511);
select*from t_dept1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/15.png?raw=true)
3.将一个表的记录插入另一个表中
执行命令如下:
```SQL
desc t_loader;
insert into t_loader values
('nike','nick','newyork',0124,8848),
('jike','jack','Los',0125,6666);
select*from t_loader;
insert into t_dept1(cname,address,tel)
select Cname,address,tel from t_loader;
select*from t_dept1;
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/16.png?raw=true)
