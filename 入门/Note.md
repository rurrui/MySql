## 优先级
NOT>AND>OR
## 聚合函数和执行顺序  
举一个栗子：  
SELECT COUNT(EX_AGE)  
FROM EXECUTIONS  
WHERE EX_AGE>50  
这个栗子会先进行WHERE过滤，然后再执行聚合函数