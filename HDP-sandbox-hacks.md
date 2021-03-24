How to change the mysql password
================================

1)
vi /etc/my.cnf  
[mysqld]
skip-grant-tables
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock
user=mysql
#### Disabling symbolic-links is recommended to prevent assorted security risks
symbolic-links=0

2) service mysqld restart

3) mysql -u root mysql

4) use mysql;  - on mysql prompt

5) update user set authentication_string=password('1111') where user='root';
   FLUSH PRIVILEGES; 
   
6) mysql -u root -p (use new password to login)
