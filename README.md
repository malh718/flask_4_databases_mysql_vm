# flask_4_databases_mysql_vm
504 homework 

# ERRORS:
It had taken me a long time and multiple tries  to connect my azure vm to the mysqlworkbench. I had had the same issue when I was following along during class, and as much as I tried it did not connect. I was sitting there for maybe 30-40 minutes redoing everything, creating new users, trying to restart, double checking each step. Then I realized I had put the wrong password into workbench the whole time. I was putting in the wrong password, and all my steps prior had been correct. This was not only incredibly frustrating but also a silly mistake, that I will not repeat. 

# Creating Virtual Machine in Azure 
- Navigate to virtual machine
- set Size to standard B1ms
- image to Ubunto server
- set region to us
- <img width="804" alt="Screen Shot 2023-10-11 at 10 56 09 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/cfbbd22a-f648-4b78-9e10-af9b3d544600">

- and create a username and password
- select all for the inbound ports
- For the disk type choose standard and yes managed disks
- Enable auto shutdown and create
- add inbound port rule for 3306 in azure
  <img width="786" alt="Screen Shot 2023-10-11 at 10 56 40 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/4e1d0487-8e93-4af1-89b6-7dcc57f9852f">

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
- From here it should connect to mysqlworkbench
<img width="936" alt="Screen Shot 2023-10-11 at 10 26 36 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/dcd9e34e-1caf-4669-824f-b2ae022a1982">
<img width="972" alt="Screen Shot 2023-10-11 at 10 26 53 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/a9901b00-db9e-430a-bbea-87e7fb082612">
<img width="973" alt="Screen Shot 2023-10-11 at 10 27 12 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/d3035bbb-769f-48a0-83c1-6803800897fe">

<img width="972" alt="Screen Shot 2023-10-11 at 10 27 26 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/33daf96e-3f02-491a-8b26-57a4a809b3d9">

<img width="962" alt="Screen Shot 2023-10-11 at 10 27 43 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/d05d30b8-9c53-42d3-93dc-dbdf6e427208">





Databases and Tables: 

Thankfully, I was able to get the VM from azure to connect and from there I was able to create a new database called "hospitals". In Hospitals there are two tables "demographics" and "patients". In this case the primary key for the first doctors table is patient_id, and the foreign key is patient_id as referenced in the doctors table. The schema chosen was "hospitals." 

<img width="812" alt="Screen Shot 2023-10-11 at 10 52 32 PM" src="https://github.com/malh718/flask_4_databases_mysql_vm/assets/102617334/c2f359c4-dac8-4db9-9a03-2297a3fb0360">


