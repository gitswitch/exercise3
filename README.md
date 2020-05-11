<b># exercise3</b>

In this exercise I cloned a git on DO community, https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-wordpress-with-lamp-on-ubuntu-18-04
I found an error on the first task and I changed
```
loop: [ 'apache2', 'mysql-server', 'python3-pymysql', 'php', 'php-mysql', 'libapache2-mod-php' ]
```
with 
```
loop: [ 'apache2', 'default-mysql-server', 'python3-pymysql', 'php', 'php-mysql', 'libapache2-mod-php' ]
```
I stuck with this error:
```
unable to connect to database, check login_user and login_password are correct or /root/.my.cnf has the credentials. Exception message: (1698, u\"Access denied for user 'root'@'localhost'\")"} 

```
I followed the suggestion on this thread https://github.com/ansible/ansible/issues/47736 and added the option login_unix_socket: /var/run/mysqld/mysqld.sock 
without success.
