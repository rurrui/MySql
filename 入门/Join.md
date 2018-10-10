# JOIN ON的使用
TABLEA 3条数据  
TABLEB 5条数据
## 默认(INNER JOIN)
1.TABLEA (INNER)JOIN TABLEB ON 1

返回15条数据，因为ON条件始终为True，表A每条数据会与表B每条数据相匹配  
2.TABLEA (INNER)JOIN TABLEB ON 0  
返回0条数据，因为ON始终为False，内连接不会进行任何匹配

## 左连接
TABLEA (INNER)JOIN TABLEB ON 0  
返回3条数据，左连接的特点是即使没有匹配到数据，依旧保留左边表的数据
## 右连接
TABLEA (INNER)JOIN TABLEB ON 0  
返回5条数据，右连接的特点是即使没有匹配到数据，依旧保留右边表的数据
## OUTER JOIN
TABLEA (INNER)JOIN TABLEB ON 0  
返回15条数据，全连接的特点是即使没有匹配到数据，依旧强行匹配两个表的数据