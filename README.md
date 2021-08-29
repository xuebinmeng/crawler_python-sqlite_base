# crawler_python-sqlite_base
python爬虫 - sqlite基础应用
=================================
python3对接嵌入式数据库sqlite

<h3>1：工具安装</h3>

python3 ->  https://www.python.org/downloads/

sqlite ->  python3自带SQLite3类库

<h3>2：代码实现sqlite基础功能</h3>

1：关系表的字段类型说明

TEXT  字符串类型

INTEGER 数值类型

BLOB  二进制数据

REAL  8字节的IEEE浮点数字

没有布尔类型，用0(false) 和 1(true)表示

2：关系表相关的DDL操作

默认就使用main数据库，可以不用新建库

建表
create table IF NOT EXISTS book(
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                Title TEXT NOT NULL ,
                Title_pic text,
                Author text,
                score integer,
                Introduction TEXT,
                press TEXT,
                create_time real,
                type text)


修改表
ALTER TABLE book ADD column remark text

删除表
drop table IF EXISTS book

3：关系表的DML操作(CRUD)

新增
insert into book(id,Title,Title_pic,score,Introduction,Author,press,create_time,type,remark)
                          values(1,"ABC杀人事件","1.pic",9.0,"1","阿加莎·克里斯蒂","新星出版社",CURRENT_TIMESTAMP,"推理小说",""),
                                (2,"无人生还","2.pic",9.0,"2","阿加莎·克里斯蒂","新星出版社",CURRENT_TIMESTAMP,"推理小说",""),
                                (3,"罗杰疑案","3.pic",9.0,"3","阿加莎·克里斯蒂","新星出版社",CURRENT_TIMESTAMP,"推理小说",""),
                                (4,"金色梦想","4.pic",9.0,"4","阿加莎·克里斯蒂","新星出版社",CURRENT_TIMESTAMP,"推理小说",""),
                                (5,"斯泰尔斯庄园奇案","5.pic",9.0,"5","阿加莎·克里斯蒂","新星出版社",CURRENT_TIMESTAMP,"推理小说","")
								
查询

select * from book

删除

delete from book where title = "金色梦想"

修改

update book set Introduction ="大侦探波洛第一次登场"  where title = "斯泰尔斯庄园奇案"

其他语法大致都是通用的sql，详情可查看https://www.runoob.com/sqlite/sqlite-tutorial.html

4：综合案例

1：删除读书表

2：新建读书表

3：添加备注字段

4: 新增5本图书内容 

5：修改名为xx的图书

6：删除名为xx的图书

7：查询图书

5：github项目地址
https://github.com/xuebinmeng/crawler_python-sqlite_base
