# Jenkins Project 1

This is a simple project to test the Jenkins pipeline using AWS.

Tools used :

- Jenkins
- SonarQube
- Maven
- Docker
- Trivy

Step 1: Create a new ubuntu instance in East-US region, with 30gb and t2.medium as configuration.
connect to instance, and sign-in as root user using command "sudo su".

Step 2: Install Jenkins by taking the command from my git repo: <br>

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/jenkins.sh

Step 3: change security group of the instance: <br>
adding security group:

![adding security group](image.png)
edit inbound rule :
![edit inbound rule](image-1.png)
adding inbound rule:
![adding inbound rule](image-2.png)

Step 3: Open the jenkins from EC2 IP Address <br>

- <IP_Address>:8080
- Get Administrator password using command "cat /var/lib/jenkins/secrets/initialAdminPassword"
  ![alt text](image-3.png)
- install plugins
  ![alt text](image-4.png)
- create user
  ![alt text](image-5.png)
  <br>
  <br>
  ![alt text](image-6.png)

- Click on New Item
  ![alt text](image-7.png)

- create new Pipeline
  ![alt text](image-8.png)

- configure the pipeline
  ![alt text](image-9.png)
  <br>
  ![alt text](image-10.png)

Step 4: Adding plugins for sonar and jfrog

![alt text](image-11.png)
<br>
![alt text](image-13.png)

list of plugins:

- sonar gerrit
- sonarqube scanner
- sonarqube generic coverage
- sonar quality gates
- quality gates
- artifactory
- jfrog

Step 5: install Docker

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/docker.sh

to check if the docker is installed or not use command "docker -v"
it will give you the docker version if it is intalled.
demo :

### root@ip-<IP-Address>:/home/ubuntu# docker -v

### Docker version 24.0.2, build cb74dfc

Step 6: install SonarQube

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/sonarqube.sh

Step 7: Open SonarQube by using IP Address and port: 9000 <br>
demo link: <IP-Address>:9000

Step 8: login into sonarqube dashboard
user : admin
password: admin
![alt text](image-14.png)

update user password
![alt text](image-15.png)

Step 9: Integration of jenkins into sonar
![alt text](image-16.png)

![alt text](image-19.png)
check the webhook if created or not.
![alt text](image-18.png)
