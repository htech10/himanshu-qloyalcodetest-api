# himanshu-qloyalcodetest-api
lightbulb api tests using newman , jenkins, aws, docker

## 1. How to run this postman collection locally using CLI 

1.1 clone the git repository
$git clone https://github.com/htech10/himanshu-qloyalc
odetest-api.git

1.2 Install dependencies: This will install newman which is a cli tool to run postman collection
$cd himanshu-qloyalcodetest-api
$npm install

1.3 Executing Tests

TestScenario1: Run 1 test with external data source that iterates the api call with power within valid range [1 , 30, 60]
$newman run tests/lightbulb-quantas.postman_collection.json --folder folder1 -d data/lightbulb-data.json

TestScenario2: Run 3 tests 
$newman run tests/lightbulb-quantas.postman_collection.json --folder folder2


### 1.4 To view the notification of Jenkins Run Join the following slack team and checkout notification is slack channel #quantas-test
https://join.slack.com/t/research-codinghat/shared_invite/enQtMzA0MDE1Mzk1MTIyLTU2OTA0MTU2Njc4NjA0NDdhY2NkMzVkNGFmMGI3NmQyOGY0MjVhODE0MmQ1OGM5ZjVjMjczMDAxMjU0MmQyMDA

## 2. How to setup this Postman collection Test Run on Jenkins

2.1 Provide project name "lightbulb-api"
2.2 Link github project url under General tab "https://github.com/htech10/himanshu-qloyalcodetest-api"
2.3 Under Source Code Management , choose Git and add the repository "https://github.com/htech10/himanshu-qloyalcodetest-api.git"
2.4 Save
2.5 Login to AWS EC2 Instance (Windows-Server RMI) to look at the configuration using Remote Destop with following credentials
Public DNS	ec2-54-206-39-99.ap-southeast-2.compute.amazonaws.com
User name	Administrator
Password	4AebuaANVuP
Note: Please note that slack notification is from the localhost instance and AWS Instance is to be debugged 

## 3. Running this Postman Collection on docker 

3.1 Pull the newman image 
$docker pull postman/newman_ubuntu1404

3.2 Run the collection using newman pulled in 3.1
$docker run -t postman/newman_ubuntu1404 run "https://www.getpostman.com/collections/3fe79793eab3faeadbe3"

Note: This "https://www.getpostman.com/collections/3fe79793eab3faeadbe3" is a link generated by postman for the same collection referred throughout this document



