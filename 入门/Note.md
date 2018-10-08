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