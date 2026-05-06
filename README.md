# 3-Tier-Application-using-AWS-services
Deployed 3 tier application using only AWS services VPC Bastion host connection with high security, scalability &amp; availability

<img width="461" height="383" alt="VPC_architecture" src="https://github.com/user-attachments/assets/8873bed7-1a11-43cb-a42e-945200eb11eb" />


<img width="1723" height="678" alt="image" src="https://github.com/user-attachments/assets/740e475a-529a-41a4-87d5-86210fab1d45" />

<img width="1758" height="735" alt="image" src="https://github.com/user-attachments/assets/be0a4ad0-08fe-4468-8b84-1b963d3bbaf0" />



---> Clone this repository into the Bastion server: git clone https://github.com/sumanthtony/Blood-Bank-App-using-docker-k8s

---> Create a **Amazon RDS** with **MYSQL** and attach our newly created **MY-VPC to RDS**

---> Edit all 6 PHP files by changing **host name** (Copy the RDS end point URL and paste here), **username:** admin, **password:** admin123

---> We need to install web server (apt install apache2 -y && systemctl enable apache2) & confirm it is running or not (systemctl status apche2) and need to send all the **EDITED PHP files** to web server path: cp -r * /var/www/html/

---> Need to install MYSQL using below commands:

sudo apt-get install php libapache2-mod-php php-mysql php-curl php-gd php-json php-zip php-mbstring -y

sudo apt-get install mysql-server -y

---> Login into MYSQL: mysql -h mysqldb.cizikgiy6mw6.us-east-1.rds.amazonaws.com -u admin -p (Copy the RDS end point url, here -h is host), after entering the password execute all the SQL queries present in the repo;  https://github.com/sumanthtony/Blood-Bank-App-using-docker-k8s


<img width="1034" height="364" alt="image" src="https://github.com/user-attachments/assets/9e2f8066-0efe-4e7f-bffb-490d9fd813f2" />


---> SINCE WE HAVE LAUNCHED 3 PRIVATE SUBNETS TO SCALE THE APPLICATIONS AUTOMATICALLY WE'LL NEED TO CREATE **ASG ==== LAUNCH TEMPLATE (We need AMI) + lOAD BALANCER (We need Target Group)**

---> Create a CUSTOM IMAGE from PRIVATE-SERVER---select---actions----image & templates---create image--Name: Bank-image (we can give any custom image)--save

Note: Wait for few minutes to be available of the IMAGE.

---> Once the AMI is available use this **AMI in launch Template** and save

---> Create a TARGET GROUP (While selecting the SERVERS SELECT PRIVATE SERVER AND CLICK ON ADD AS PENDING BELOW OPTION & SAVE) & save---and create a LOAD BALANCER (While selecting Availability Zones ensure we are selecting PUBLIC-SUBNETS ONLY, because we can't attach PRIVATE-SUBNETS to the load balancers) and use this Target Group here.

---> Once the LOAD BALANCER is available copy the DNS name and paste in the browser we can able to access the BLOOD BANK APPLICATION.

---> For scalability create a **Auto Scaling Group** and use launch template, target group, load balancer here and we can see based on the DESIRED number of servers we have given those will be created automatically in EC2 console.

---> We can access the application using ASG created instances IP ADDRESS as well.

                    ==== BELOW IS THE OUTPUT OF THE APPLICATION AND WHEN USER CREATES THE ACCOUNT DATA IS STORED IN THE MYSQL DATABASE ====


<img width="1563" height="908" alt="image" src="https://github.com/user-attachments/assets/bc3c4878-9a36-4c08-83d6-4bdfef0172f5" />



<img width="882" height="318" alt="image" src="https://github.com/user-attachments/assets/cf43c30a-c3e6-4254-9c01-e2931a488d39" />












