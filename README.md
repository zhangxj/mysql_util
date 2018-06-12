# mysql_util
python setup.py sdist bdist_egg upload


```
pip install mysql_util
# 导入工具包
from mysql_util import mysql_util

# 数据库连接配置
conn_cond = dict(db_host="localhost", db_user="root", db_password = "root", db_name = "robot")

# 根据sql 获取数量
print mysql_util.m_count("select count(*) from user", **conn_cond)
# 根据sql 查询单条记录
print mysql_util.m_query_one("select id, appid, name from user where id=10", fields = ['id', 'appid', 'name'], **conn_cond)
# 根据sql 获取列表，支持分页 page_index 第几页, page_size 每页多少数据, 如果指定findall = True,则返回所有数据
data, page = mysql_util.m_query("select id, appid, name from user", fields = ['id', 'appid', 'name'], **conn_cond)
print data
print page

```
