## 优先级
NOT>AND>OR
## 聚合函数和执行顺序  
举一个栗子：  
SELECT COUNT(EX_AGE)  
FROM EXECUTIONS  
WHERE EX_AGE>50  
这个栗子会先进行WHERE过滤，然后再执行聚合函数
## 聚合函数、GROUP BY和WHERE  
如果我们现在有一个省市联动数据库，
要求是查询出每个省有多少个城市，并且有一个条件，查询出来的每个市的人口要大于500万  
``` 
SELECT PROVINCE
COUNT(*) CITY_NUMS
FROM CHINA
WHERE POPULATION>5000000
GROUP BY PROVINCE
```
在这里我们说一下它的执行顺序，where过滤条件是最先执行的，其次才是GROUP BY分组  
## HAVING
HAVING的使用场合：  
当你需要使用GROUP BY后的某一列进行过滤操作的时候，你不能在WHERE中使用，因为WHERE总是在GROUP BY之前就进行过滤，这个时候就需要使用HAVING来利用GROUP BY后的过滤了  
## 执行顺序
WHERE>GROUP BY>HAVING
## SQL中的Map/Reduce
Map:  
执行这一条SQL语句：  
SELECT LENGTH(NAME) FROM CITY  
在这里我们的LENGTH对NAME执行了操作，并且是对每一行的NAME都进行了操作，因此在SQL里这就是一个Map的使用实例  
Reduce:  
执行这一条SQL语句：  
SELECT DITRICT,COUNT(*)  
FROM CITY  
GROUP BY DISTRICT    
WHERE CD='CHN'
在这里，我们可以查找出中国每一个省有多少座城市，而GROUP BY在这里相当于执行了Reduce操作  
因为我们把DISTRICT相同的多行通过GROUP BY聚合成了一个组，也就是一个DISTRICT值现在就能代表所有DISTRICT列相同的行  
映射到Reduce的概念：  
Reduce is a function which "collects" the items in lists and perform some computation on all of them, thus reducing them to a single value.  
我们发现与之正好对应，所以在这里GROUP BY相当于执行的是Reduce的功能