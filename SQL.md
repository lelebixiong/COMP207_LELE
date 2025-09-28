**SQL的三个主要部分**：
- DDL（数据定义语言 Data Definition Language）：创建/修改/删除数据库和表
- DML（数据操作语言 Data Manipulation Language）：增删改查表中的数据
- Transact-SQL：执行SQL语句序列
**表的结构**：
- 表名（如：Employees, Items）
- 属性/列（Attributes/Columns）：每列包含相同数据类型
- 元组/行（Tuples/Rows）：每行代表一个实体或关系
- 模式（Schema）：表的结构定义，如 Employees(birthday, first_name, family_name)



SQL DDL（数据定义语言） 
	 **创建数据库**：`CREATE DATABASE databasename;
	 **创建表**：定义表结构、数据类型和约束
	 **数据类型**：
		- INT（整数）  
		- FLOAT（小数）  
		- VARCHAR(x)（可变长度字符串）  
		- DATE（日期，格式：YYYY-MM-DD）  
		- DATETIME（日期时间，格式：YYYY-MM-DD HH-MI-SS）
		- XML: for XML files
		- BLOB: binary files
		- 
	**约束条件**：
		- **UNIQUE**：确保列值唯一 ，可以为NULL。
		- **PRIMARY KEY**：主键，用于唯一标识每行并决定物理存储排序,不能为NULL 
		- **FOREIGN KEY**：外键，用于链接两个表，确保数据引用完整性  
	**修改和删除**：
		- ALTER TABLE：修改表结构  
				- ALTER TABLE Employees MODIFY age VARCHAR(3) NOT NULL(把 age 列从 INT 改成 VARCHAR(3)，并且不允许 NULL);  
		- DROP：删除数据库或表  、
				- DROP DATABASE CS_Store/DROP TABLE Emplyees  



SQL DML（数据操作语言，不含查询）
	 **INSERT**：插入数据
		 INSERT INTO Students VALUES ('Oliver', 20171112, 'G402') /  INSERT INTO Students(programme, name) VALUES ('G402',20171112); ; 
	**DELETE**：删除数据
		 DELETE FROM Students WHERE name='John';
	**UPDATE**：更新数据
		UPDATE Students SET programme='G402' WHERE name='Oliver'; 
**WHERE子句条件**：
		- 比较运算符：=, <, >, <=, >=, <>  
			- SELECT * FROM Employees WHERE family_name = 'Smith'(查找姓氏是 'Smith' 的员工);  
			- SELECT * FROM Employees WHERE salary < 5000(查找工资低于 5000 的员工);
			- SELECT * FROM Employees WHERE birthday <= '2000-01-01'(查找出生日期在 2000-01-01 之前或当天的员工);
			- SELECT * FROM Employees WHERE family_name <> 'Wang'(查找姓氏不是 'Wang' 的员工);
		- 逻辑运算符：AND, OR, NOT  
			-  SELECT * FROM Employees WHERE salary > 5000 AND department = 'IT'(查找工资大于 5000 且部门是 'IT' 的员工);
			- SELECT * FROM Employees WHERE NOT department = 'IT'(查找不是 IT 部门的员工);
		- 其他：BETWEEN, LIKE（模式匹配）, IN（列表匹配）  
			- SELECT * FROM Employees WHERE salary BETWEEN 5000 AND 10000;(查找工资在 5000 到 10000 之间的员工（含边界))
			- SELECT * FROM Employees WHERE family_name LIKE 'Li%'(查找姓氏以 'Li' 开头的员工);
			- SELECT * FROM Employees WHERE first_name LIKE '_a%'(查找名字里第二个字母是 'a' 的员工);
			- SELECT * FROM Employees WHERE department IN ('HR', 'IT', 'Finance')(查找部门在 HR、IT、Finance 里的员工);



文档特别强调了**SQL注入**攻击的危险性 - 这是网络上最常见的安全漏洞（约占所有漏洞的50%）。当用户输入直接拼接到SQL语句中时，恶意用户可能通过特殊构造的输入来破坏或窃取数据。
## 实践要点
		1. SQL关键字不区分大小写  
		2. 字符串需要用单引号括起来  
		3. 注释使用 -- 符号  
		4. 在WHERE子句中的等号(=)是比较操作，在SET子句中的等号是赋值操作  