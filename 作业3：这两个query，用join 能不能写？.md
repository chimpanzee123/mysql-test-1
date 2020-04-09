作业3：这两个query，用join能不能写？
1.两个query
第一个query
执行命令如下：
```SQL
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.hiredate,t1.salary,t1.comm    
        from t_employee t1 inner join t_employee2 t2 
                on t1.sal>t2.salary and (t2.ename='SMITH');                       
select * from t_employee;               
select * from t_employee where salary > (
select salary from t_employee where ename='SMITH');
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/3-1.png?raw=true)
第二个query可以这样
执行命令如下：
```SQL
select * from t_employee where (salary, job) = (
select salary,job from t_employee where ename = 'smith');               
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.hiredate,t1.salary,t1.comm          
            from t_employee t1 inner join t_employee t2 
                  on (t1.salary = t2.salary and (t2.ename='SMITH')) and (t1.job = t2.job and (t2.ename='SMITH'));       
select * from t_employee;  
```
执行上面SQL语句结果显示如图所示：
![](https://github.com/chimpanzee123/mysql-test-1/blob/master/3-2.png?raw=true)
