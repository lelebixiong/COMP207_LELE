# COMP207_LELE# 📦 MySQL 数据库项目介绍

## 📖 项目简介
本项目是一个基于 **MySQL** 设计的数据库，用于展示和管理 [👉 在这里填写你的应用场景，例如：汽车销售公司数据库 / 港口公司数据库 / 学生选课系统 等]。  
主要目标是提供 **数据存储、查询、约束管理**，并支持高效的增删改查操作。

---

## 📂 数据库结构
数据库名称：`my_database`

### 🔑 主要数据表
| 表名 | 功能描述 |
|------|----------|
| `Employees` | 存储员工的基本信息 |
| `Departments` | 存储部门信息 |
| `Projects` | 存储项目/任务相关信息 |
| `Enrollments` | 存储报名/参与关系（举例） |

---

## 🛠 表结构定义（部分示例）

### 1. Employees 表
```sql
CREATE TABLE Employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    birthday DATE,
    department_id INT,
    CONSTRAINT fk_dept FOREIGN KEY (department_id) REFERENCES Departments(dept_id)
);
```

🚀 使用方法
1. 克隆项目
git clone https://github.com/你的用户名/你的仓库名.git
cd 你的仓库名

2. 导入数据库
mysql -u root -p my_database < schema.sql

3. 测试查询
SELECT * FROM Employees;

👨‍💻 作者信息

姓名：lelebixiong
邮箱：xiyuan.chen23@qq.com
GitHub：https://github.com/lelebixiong/
