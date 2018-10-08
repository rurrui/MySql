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