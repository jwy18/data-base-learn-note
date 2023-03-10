# data-base-learn-note
数据库数据具有永久存储、有组织、可共享三个基本特点
数据库管理系统主要功能：数据定义；数据组织、存储和管理；数据操纵；数据库的事务管理和运行管理等
数据独立性：物理独立性：用户的应用程序与数据库中数据的物理存储是相互独立的
           逻辑独立性：用户的应用程序与数据库的逻辑结构是相互独立的
逻辑模型：是按计算机系统的观点对数据建模，主要用于数据库管理系统的实现。包括层次模型、网状模型、关系模型
物理模型：数据在系统内部的表示方法和存取方法。
ER图分为实体、属性、关系三个核心部分。实体是长方形，属性是椭圆形，关系为菱形
三级模式结构：外模式+模式+内模式
外模式：用户看到和使用的
模式：也称为逻辑模式，是数据库中全体数据的逻辑结构和特征的描述 ，是所有用户的公共数据视图。
内模式：也称存储模式，一个数据库只有一个内模式。

关系是一张表，二维表
可以形象的表示为R(U,D,DOM,F)
R:关系名，U：所有属性名，D：属性来自哪些域，DOM：属性和域的映射，F：属性间的依赖关系
关系语言的分类：
分为关系代数语言，关系演算语言，SQL语言
关系代数三大要素：运算对象（关系），运算符，运算结果（关系）
关系代数运算：并，差，笛卡尔积，选择，投影及交，连接，除
选择：σCredit>3（Course）
投影：ΠSname,Sdept(Student)
找95001号学生所选修的课程号
ΠCno（σSno='95001'(SC))
自然连接：把共同属性进行等值连接
外连接 保留悬浮元组
左外连接 保留左边的悬浮元组
右外连接 保留右边的悬浮元组
除 保留R中满足S的，并且R中列要去掉S的列

关系完整性
1实体完整性
           主码唯一且非空
2参照完整性
外码要么为空，要么对应另一表的主码
3用户定义完整性
自己写的完整

SOL语言
数据定义语言DDL
 主要用来定义逻辑结构，包括定义基表，视图和索引。
删除表 定义表 修改表

数据查询语言DQL
 主要用来对数据库中的各种数据对象进行查询。

数据控制功能DCL
 对表和视图的授权、完整性规则以及事务开始和结束等控制语句。

SQL语言特点
综合统一、高度非过程化、面向集合的操作方式、以同一种语法结构提供两种使用方式、语言简洁

模式定义
 CREATE SCHEMA<模式名>AUTHORIZATION<用户名>;

模式定义+视图
 CREATE SCHEMA<模式名>AUTHORIZATION<用户名>[<表定义子句>|<视图定义子句>|<授权定义子句>]

模式删除
DROP SCHEMA<模式名><CASCADE|RESTRICT>

数据库不安全因素：
非授权用户对数据库的恶意存取和破坏；
数据库中重要数据的泄露；
安全环境的脆弱性；

把查询权限授给用户U1： GRANT SELECT ON TABLE STUDENT TO U1;
把用户U4修改学生学好的权限收回：REVOKE UPDATE(Sno) ON TABLE STUDENT FROM U4;

事务的4个特性：
原子性：不可分割；
一致性：事务的执行结果必须一致；
隔离性：一个事务的执行不能被其他事务干扰；
持续性：一个事务一旦提交，他对数据库中数据的改变是永久性的。

数据库系统的故障种类：
事务内部的故障；
系统故障；
介质故障；
计算机病毒。

数据库恢复技术：
数据转储；
登记日志文件。








