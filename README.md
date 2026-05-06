# 3-Tier-Application-using-AWS-services
Deployed 3 tier application using only AWS services VPC Bastion host connection with high security, scalability &amp; availability

<img width="461" height="383" alt="VPC_architecture" src="https://github.com/user-attachments/assets/8873bed7-1a11-43cb-a42e-945200eb11eb" />


<img width="1723" height="678" alt="image" src="https://github.com/user-attachments/assets/740e475a-529a-41a4-87d5-86210fab1d45" />

<img width="1758" height="735" alt="image" src="https://github.com/user-attachments/assets/be0a4ad0-08fe-4468-8b84-1b963d3bbaf0" />



---> Clone this repository into the Bastion server: git clone https://github.com/sumanthtony/Blood-Bank-App-using-docker-k8s

---> Create a **Amazon RDS** with **MYSQL** and attach our newly created **MY-VPC to RDS**

---> Edit all 6 PHP files by changing **host name** (Copy the RDS end point URL and paste here), **username:** admin, **password:** admin123

---> We need to install web server (apt install apache2 -y) & confirm it is running or not (systemctl status apche2) and need to send all the **EDITED PHP files** to web server path: cp -r * /var/www/html/

---> Need to install MYSQL using below commands:

sudo apt-get install php libapache2-mod-php php-mysql php-curl php-gd php-json php-zip php-mbstring -y

sudo apt-get install mysql-server -y

---> Login into MYSQL: mysql -h mysqldb.cizikgiy6mw6.us-east-1.rds.amazonaws.com -u admin -p (Copy the RDS end point url, here -h is host), after entering the password execute all the SQL queries present in the repo;  https://github.com/sumanthtony/Blood-Bank-App-using-docker-k8s





