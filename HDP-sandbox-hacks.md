How to change the mysql password
================================

<p>
1) vi /etc/my.cnf  <br />    
[mysqld]           <br /> 
skip-grant-tables  <br /> 
datadir=/var/lib/mysql  <br /> 
socket=/var/lib/mysql/mysql.sock  <br /> 
user=mysql   <br /> 
#### Disabling symbolic-links is recommended to prevent assorted security risks  <br />  
symbolic-links=0   <br /> 
</p>

2) service mysqld restart

3) mysql -u root mysql

4) use mysql;  - on mysql prompt

5) update user set authentication_string=password('1111') where user='root';
   FLUSH PRIVILEGES; 
   
6) mysql -u root -p (use new password to login)


