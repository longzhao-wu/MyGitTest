## mysql

查看表结构命令：**DESCRIBE** 表名; **DESC** 表名; EXPLAIN 表名; **SHOW** COLUMNS **FROM** 表名; **SHOW** FIELDS **FROM** 表名;

改表名命令：ALTER **TABLE** 旧表名 RENAME **TO** 新表名; RENAME **TABLE** 旧表名1 **TO** 新表名1, 旧表名2 **TO** 新表名2, ... 旧表名n **TO** 新表名n;



INSERT INTO 表名(列1, 列2, ...) VALUES(列1的值，列2的值, ...);  可以指定部分列，没有被显示指定的列的值将被设定为null

主键 外键  unique约束  

AUTO_INCREMENT属性

1. 一个表中最多有一个具有AUTO_INCREMENT属性的列。
2. 具有AUTO_INCREMENT属性的列必须建立索引。主键和具有`UNIQUE`属性的列会自动建立索引。不过至于什么是索引，在学习MySQL进阶的时候才会介绍。
3. 拥有AUTO_INCREMENT属性的列就不能再通过指定DEFAULT属性来指定默认值。
4. 一般拥有AUTO_INCREMENT属性的列都是作为主键的属性，来自动生成唯一标识一条记录的主键值。

父表中被子表依赖的列或者列组合必须建立索引，如果该列或者列组合已经是主键或者有UNIQUE属性，那么它们也就被默认建立了索引。示例中student_score表依赖于stuent_info表的number列，而number列又是stuent_info的主键（注意上一章定义的student_info结构中没有把number列定义为主键，本章才将其定义为主键，如果你的机器上还没有将其定义为主键的话，赶紧修改表结构呗～），所以在student_score表中创建外键是没问题的。 当然至于什么是索引，不是我们从零蛋开始学习**MySQL**的同学们需要关心的事，等学完本书之后再去看《**MySQL**是怎样运行的：从根儿上理解**MySQL**》就懂了。

