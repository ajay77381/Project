Project 1 - Deploying a Multi-Tier Website Using AWS EC2
1- Create a VPC
2- Create 2 Public subnet( we need atleast 2 AZs for ELB) and 1 private subnet------ Public1 and private subnet should be in same AZs
3- create a IGW and attach to VPC
4- Create a NAT in Public1-subnet
5- Create private and public Route Tables ------ edit the routes and associate it
6- Create one Bastion Host in public1 subnet and Appliaction instance in your private subnet.
7- Create a S3 bucket
8- Create RDS(mysql)
9- Create a dynamoDb table(Name of the table should be same as line 86 of the github code(https://github.com/Training-demo/aws-code-main)<EmpApp.py>), Partition key shoould be same as line 88 and change from string to number.
10- Create A hosted Zone(Route53)------ Copy paste the Name Servers from your hosted zone to DN.
11- Create a Record---- Select Application Load Balancer---> Your Region--> Your Load Balancer(A-type record)
12- Create A IAM ROLE(s3fullaccess, dynamoDb full access, Rds Full access)
13- Come to application instance- selecct your application instance---> Actions--> security--> modify IAMRole--> Attach your role
14- login into your Bastion Host---> nano key--> paste the key--> chmod 400 key--> ssh -i key ubuntu@private ip of application instance
15- sudo apt-get install mysql-client.
16- sudo mysql -h (endpoint of your RDS) -u admin -p (give the password)
17- show databases;------>use Db(name)----> show tables;(table will be empty)
18- create table employee(emp_id VARCHAR(20), first_name VARCHAR(20), last_name VARCHAR(20), primary_skills VARCHAR(20), location VARCHAR(20));
19- describe employee;
20- git clone (paste the code link from the gitHub)
21- 1 git clone https://github.com/Training-Demo/aws-code-main.git
    2  ls
    3  cd aws-code-main
    4  ls
    5  nano config.py
    6  nano EmpApp.py (Check or search for DynamoDb and change the region according to you---which region you are working in)
    7  history
22- Install the dependencies from the gitHub

