## 项目维护地址
https://github.com/222momo/yam_fdw
## 项目原址
https://github.com/asya999/yam_fdw
### tips：作为原项目的补丁，该项目已年久失修，无法联系作者提交补丁，因此，在本项目中做一些更新
## 1.修改项目支持python3语法
__init__.py
```
加入
from functools import reduce

for x in xrange(docCount):
改成
for x in range(docCount):
```

Yet Another Postgres FDW for MongoDB 
====================================
based on [multicorn](http://multicorn.org)

How to use:
----------

```
Install Postgres
Install Multicorn
sudo python setup.py install

CREATE EXTENSION multicorn;
CREATE create SERVER mongodb_proxy_server FOREIGN DATA WRAPPER multicorn OPTIONS (wrapper 'yam_fdw.Yamfdw');
CREATE FOREIGN TABLE foo ( "_id" varchar OPTIONS (type 'ObjectId'), f1_f2 numeric OPTIONS (mname 'a.b'), d varchar )
   SERVER mongodb_proxy_server OPTIONS ( db 'test', collection 'foo' [, host 'hostNameOrIp', port: '27017', user 'myusername', password 'mypassword' ] );

```
