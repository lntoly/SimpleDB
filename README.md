#Course Project of Compiler Theory
##TODO
project name


修改数据库部分的时候，发现了几个BUG，如下：

1.select * 出现错误
select * from student where time > 11;
返回的statement中的prop_list 为空


2.create table student(sid int, primary key (sid), age int, time int)
返回的prop_list为[sid, sid, age, time]
然而
create table student(primary key (sid), age int, time int)（语法错误）
返回的prop_list为[sid, age, time]

3.大于符号“>”得到的解析符号是LT，比如出现
select sid, age, time  from student where time > 11;
得到的布尔树为： time LT 11

4.无法识别!=， 比如出现
select sid, age, time  from student where time != 11;
直接崩掉
                                                                                                                ---栋梁：）