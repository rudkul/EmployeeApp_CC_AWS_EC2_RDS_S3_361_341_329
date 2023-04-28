# Cloud Computing Course Project - Project Number 3

# Problem Statement:
# Deployment of Web App Using AWS Cloud

This problem statement has the following objectives:
- Create web applications and seamlessly integrate them with cloud services for optimal performance and scalability.
- Acquire expertise in deploying databases to the cloud and harness the benefits of cloud-based data management for enhanced reliability, accessibility, and cost-efficiency.
- Understand how to use AWS for deployment

## Requirements:
- Basic Knowledge of **Web Development**.
- Good Understanding of **Git/GitHub**.
- Basic Understanding of **AWS**.
- Database Fundamentals in **SQL**, **NoSQL**.

## Tasks
0. ### Task 0 - Setting Up **AWS Budgets**	
	-	**AWS Budgets** allows you to track your costs, usage, and coverage with custom budgets. It keeps the users informed on forecasted expenditures and resource use in **AWS**. It also creates custom actions to prevent overages, inefficient resource use, or lack of coverage.
	- To make sure that the usage of the **AWS** is within the free tier, **AWS Budgets** must be used.
	- Refer to these links for understanding **AWS Budgets** in-depth and also to understand how to create AWS Budgets.
		- [What is AWS Budgets?](https://aws.amazon.com/aws-cost-management/aws-budgets/)
		- [How to control AWS Costs](https://aws.amazon.com/getting-started/hands-on/control-your-costs-free-tier-budgets/)
		- [How to Create and manage AWS Budgets](https://www.youtube.com/watch?v=UB1dlP_7arA)

1. ### Task-1 - Develop Web Application
- Develop a **basic CRUD Web Application**. Tech Stack is based on one's choice (Frontend, Backend, and Database).  
- It can be a **Single Page Application** where all the operations can be performed on the same page.
- Examples: To-do list, User Management, Bank Management.
- A **simple but proper schema** should be shown for understanding the database design. 

2. ### Task-2 - Deploying the database in AWS.
  - Determine a suitable database(eg. MySQL, PostgreSQL, etc) for the web application and create the required tables. **Aurora** should not be used as it's a paid service in AWS.
  - In this Project, you are to use **AWS RDS**. No other methods are allowed 
  - **AWS RDS** is a collection of managed services that makes it simple to set up, operate, and scale databases in the cloud. For more information, refer to this [link](https://aws.amazon.com/rds/).
  - The web application created in Task 1 must be connected to the database setup in **AWS RDS**. 
  -  Note: Please make sure that the DB instance used is **db.t2.micro, db.t3.micro, and db.t4g.Micro** Instance and it should be **single-AZ**. This is to make sure that the **RDS** instance lies in the free tier.
  - Refer to these links for understanding how to setup **RDS** :
	  - [how to setup aws RDS in node JS(can be for any backend, setup is almost the same)](https://dev.to/kevin_odongo35/aws-rds-mysql-express-vue-and-node-jfj)
	  - [How to use AWS RDS in Free tier](https://aws.amazon.com/rds/free/)
	

3. ### Task-3 - Deploying Web Application in EC2 instance.
- In this Project, you are to use an **AWS EC2** instance for deploying the web application.
- **AWS EC2**, short for **Elastic Compute Cloud**, provides scalable computing capacity. It is used to create and run virtual machines in the cloud (instances). It is designed to make web-scale cloud computing easier for developers and easy deployment of websites for small-scale websites.
- This deployment must include the integration of **GitHub actions** and is to be deployed with **Nginx**.
- **GitHub Actions** is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository or deploy merged pull requests to production.
- **Nginx** is a web server that can also be used as a reverse proxy, load balancer, mail proxy, and HTTP cache.
- Refer to the following links for understanding how the above-mentioned components work.
	- [How to use AWS EC2 in Free tier](https://aws.amazon.com/ec2/pricing/)
	- [Github Actions](https://docs.github.com/en/actions)
	- [Nginx](https://www.nginx.com/)
	- [Deploy React App using EC2](https://jasonwatmore.com/post/2019/11/18/react-nodejs-on-aws-how-to-deploy-a-mern-stack-app-to-amazon-ec2)
	- [integrate node js app with GitHub actions](https://dev.to/stretch0/deploy-your-node-app-to-ec2-with-github-actions-h9a)

### Notes:
1. Though card details are needed, **no money will be debited from the account**. It is advisable not to use the main account, use an account with a low balance.
2. Kindly **refrain from using an elastic IP address** as it's a paid service.
3. Even though the above document has steps for the deployment of web apps using react JS and node JS, you are **free to use any framework**.
4. Make sure that you **stick to the AWS free tier** throughout the implementation and demo of the project. 


# Flow of Project:
### User -> Domain Name of Web App built of Flask -> Route 53 -> EC2 -> RDS & S3

# Tasks Achieved:
## Task 0:
#### Applied budgets to the AWS console. Utilized only "free-tier eligible" features of AWS. The likes of t2.micro, t3.micro were used which fell into the free-tier of products. Utilized the EC2, S3 buckets, RDS as well as Route 53 features all coming within the free-tier of AWS products.

## Task 1:
#### Basic Employee Management System was developed using Flask. We used Flask and basic HTML, CSS to develop our Web App. It is a near-single page application with some acknowledgement pages following the landing page. All CRUD functionalities have been implemented in this Web App.

## Task 2:
#### Utilized MySQL as our database for this project. MySQL was integrated into the Flask Application for all the database manipulations. We used AWS RDS functionality to build and host our MySQL database on AWS. The Web App created is connected to RDS and the changes are reflected live on the S3 Buckets as well as the server instance. We were careful in choosing only the features that fall under the free-tier belt while building the RDS functionality for our Web App.

## Task 3:
#### We have utilized AWS EC2 to deploy our web application. We have also used AWS S3 functionality to create buckets to help us better hold our data for our Web Application. We also used Route 53 for all our connectivity solutions including load balancing (which is done by EC2 itself too), HTTP cache, linking a custom domain name to our Web App and even preventing security threats. 

# To connect to the AWS Instance using SSH:
ssh -i /path/<key_pair>.pem <username_based_on_server_os>@<public_ipv4> 


# To connect to the MySQL database on AWS RDS:
mysql -h <RDS endpoint URL> -u <master_username> -p


A password prompt will come up. Enter your password to access the MySQL RDS Database.

# To run the Flask Web App:
## Reuired Dependencies
sudo apt-get update

sudo apt-get install mysql-client

sudo apt-get install python3

sudo apt-get install python3-flask

sudo apt-get install python3-pymysql

sudo apt-get install python3-boto3


## Run the application using:
sudo python3 EmpApp.py
