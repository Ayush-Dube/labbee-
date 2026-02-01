## ✨Lab1

- MariaDB is a fork of MySQL, created by the original developers of MySQL. It's designed to be a drop-in replacement for MySQL, meaning it's fully compatible with MySQL syntax and operations.
- MariaDB was created to ensure that a truly open-source version of MySQL would always be available. It maintains high compatibility with MySQL while also offering some unique features and improvements.
- For the purposes of this lab and most basic to intermediate MySQL operations, you can treat MariaDB exactly as you would MySQL. All the commands we'll use in this lab work identically in both MariaDB and MySQL.
- MariaDB is often considered more lightweight and faster than MySQL, which makes it an excellent choice for learning environments like this lab. You might notice quicker response times, which can make your learning experience smoother.
- Many Linux distributions, including some versions of Ubuntu, now use MariaDB as their default MySQL-compatible database system due to its open-source nature and performance benefits.

🔻 Tasks
1. Start the MySQL service
2. Connect to MySQL as the root user
3. List all databases in the system
4. Select and explore the mysql system database̥
5. List all tables in the mysql database
6. Save the list of tables to a file named system_tables.txt in the ~/project directory, which has been created for you.

🟢
```shell
sudo apt update
sudo
```

![alt text](image-4.png)

tee comman❓❓❓❓

>use of sleep command

1. Using   `INTO OUTFILE`
    - permission issue
    - no overwrite

2. Redirect output to a file using `-e`
    - best 
    - less likely to cause issue
 
> Explore \G , \t , \ , -e , -p  

3. tee command


### BEST & SAFE OPTION (Industry preferred)
```sql
mysql -u root -p mydb \
-e "SELECT * FROM students;" \
> /home/labex/project/outG.txt
```
table format

```sql
mysql -u root -p mydb -t \
-e "SELECT * FROM students;" \
> outG.txt

```

## ✨Lab2

By completing this lab, you will be able to:

- Create and drop databases using various methods
- Select and switch between databases
- Retrieve important metadata about your MySQL server and databases
- Understand the case-sensitivity of database names in MySQL


>🧠  
There is no difference in database creation whether executed from (none) state or another database.  
CREATE DATABASE works at server level, not database level.