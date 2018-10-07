## %
%toy的作用是以toy结尾，toy之前可以有任意个字符
## _
_toy的作用是以toy结尾，toy之前只可以有一个字符
## 反引号``
如果数据库的表名和列名与关键字冲突了，可以使用反引号把表名列名包起来，像这样：  
SELECT `SELECT` FROM `FROM` WHERE `WHERE`='123'