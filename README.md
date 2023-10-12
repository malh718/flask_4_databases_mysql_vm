# flask_4_databases_mysql_vm
504 homework 

#Creating Virtual Machine in Azure 
- Navigate to virtual machine
- set Size to standard B1ms
- image to Ubunto server
- set region to us
- and create a username and password
- select all for the inbound ports
- For the disk type choose standard and yes managed disks
- Enable auto shutdown and create
- add inbound port rule for 3306 in azure
- from here in your google cloud shell update the ubuntu server and get sudo apt get update
- then install mysql using sudo apt install mysql-server mysql-client
y

-from here log in 
-create a new user using CREATE USER ‘dba'@'%' IDENTIFIED BY ‘ahi2020’;
-confirm using select user from mysql.user;
-test the connection using mysql -u dba -p
- it says access denied and it shows that mysql installed properly

