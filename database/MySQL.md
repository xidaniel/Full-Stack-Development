# MySQL

https://flaviocopes.com/mysql-how-to-install/

brew install mysql

---

address: 127.0.0.1:3306

```markdown
                   SQL
|MySQL Client|  --------> |MySQL Server|
                   TCP
```

---

**Using MySQL:**

 1. start & stop: 

    ```
    brew services start mysql
    brew services stop mysql
    ```

2. Setting

   ```
   mysql_secure_installation
   pw: daniel123
   ```

3. start & stop

   - This will start MySQL and will keep it running until the computer is shut down, or until you run:

   ```
   mysql.server start
   mysql.server stop
   ```

4. connect to server

   ```
   mysql -u root -p
   ```

5. Note that we are connected using the **`root`** user, which should only be used for administration purposes.

   Day to day use of a database should be done using a normal user. We’ll see it in a separate tutorial.

6. Create new database

   ```
   show databases;
   create database travel_agency;
   use travel_agency
   ```

7. User Permissions

   https://flaviocopes.com/mysql-user-permissions/

   ```
   create user 'user'@'localhost' identified by 'Daniel@3317';
   //give all privileges
   grant all privileges on traver_agency.* to 'user'@'localhost';
   ```

 8. Install Mysql Workbench

     1. **GUI management tool:**

---

**数据类型:**

https://www.runoob.com/mysql/mysql-data-types.html

---

**对应关系:**

一对多 one to many

多对多 many to many

- 通过创建一个中间表来衔接

---

**索引**

- 是关系数据库中对某一列或多个列的值进行预排序的数据结构. 使用索引可以不用扫描整个表,大大加快查询速度.

---

使用

- 创建
- 查询
  - 分页查询
  - 聚合查询
  - 连接查询
- 增加
- 删除
- 修改
- 排序

---

管理MySql

```sql
SHOW DATABASES;
CREATE DATABASE test;
DROP DATABASE test;
USE test;
SHOW TABLES;
DESC students;
SHOW CREATE TABLE students;
```

---

事务transaction

类似于银行转账, 我账户减少100,另外一个账户增加100. 整个过程叫transaction.

```sql
BEGIN;
do something
COMMIT;
```

