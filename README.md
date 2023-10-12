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
- This part is really important because if it is not installed properly than you cant get to the work bench.
- from here you can show database once ur in mysql
- from here you can try connecting to mysql workbench and make sure all the users and the ip address match
- ADD sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
- and then add to restart once you changed both of the ip address to 0.0.0.0
- and restart mysql:/etc/init.d/mysql restart
<img width="936" alt="Screen Shot 2023-10-11 at 10 26 36 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/dcd9e34e-1caf-4669-824f-b2ae022a1982">
<img width="972" alt="Screen Shot 2023-10-11 at 10 26 53 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/a9901b00-db9e-430a-bbea-87e7fb082612">
<img width="973" alt="Screen Shot 2023-10-11 at 10 27 12 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/d3035bbb-769f-48a0-83c1-6803800897fe">

<img width="972" alt="Screen Shot 2023-10-11 at 10 27 26 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/33daf96e-3f02-491a-8b26-57a4a809b3d9">

<img width="962" alt="Screen Shot 2023-10-11 at 10 27 43 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/d05d30b8-9c53-42d3-93dc-dbdf6e427208">

- From here it should connect
#ERRORS:
It had taken me a long time to connect my azure vm to the mysqlworkbench. I had had the same issue when I was following along during class, and no matter how many times I had tried it did not connect. I was sitting there for maybe 30-40 minutes redoing everything, creating new users, trying to restart, double checking each step. Then I realized..... I had put the wrong password into workbench the whole time. I was putting in the wrong password, and all my steps prior had been correct. This was a really important lesson for me and I will never make it again. 
