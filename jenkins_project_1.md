# Jenkins Project 1

## This is a simple project to test the Jenkins pipeline using AWS.

Tools used :
---
- Jenkins
- SonarQube
- Maven
- Docker
- Trivy

**Step 1:** Create a new ubuntu instance in East-US region, with 30gb and t2.medium as configuration.
connect to instance, and sign-in as root user using command "sudo su".

**Step 2:** Install Jenkins by taking the command from my git repo: <br>

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/jenkins.sh

**Step 3:** change security group of the instance: <br>
adding security group:

![adding security group](image.png)
edit inbound rule :
![edit inbound rule](image-1.png)
adding inbound rule:
![adding inbound rule](image-2.png)

**Step 4:** Open the jenkins from EC2 IP Address <br>

- <IP_Address>:8080
- Get Administrator password using command "cat /var/lib/jenkins/secrets/initialAdminPassword"
  ![alt text](image-3.png)
- install plugins
  ![alt text](image-4.png)
- create user
  ![alt text](image-5.png)
  <br>
  <br>
  <!-- ![alt text](image-6.png) -->

  ![alt text](image-17.png)

- Click on New Item
  ![alt text](image-7.png)

- create new Pipeline
  ![alt text](image-8.png)

- configure the pipeline
  ![alt text](image-9.png)
  <br>
  ![alt text](image-10.png)

**Step 5:** Adding plugins for sonar and jfrog

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

**Step 6:** install Docker

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/docker.sh

to check if the docker is installed or not use command "docker -v"
it will give you the docker version if it is intalled.
demo :

### root@ip-<IP-Address>:/home/ubuntu# docker -v

### Docker version 24.0.2, build cb74dfc

**Step 7:** install SonarQube

> repo link : https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/sonarqube.sh

**Step 8:** Open SonarQube by using IP Address and port: 9000 <br>
demo link: <IP-Address>:9000

**Step 9:** login into sonarqube dashboard
user : admin
password: admin
![alt text](image-14.png)

update user password
![alt text](image-15.png)

**Step 10:** Integration of jenkins into sonar
![alt text](image-16.png)

![alt text](image-19.png)
check the webhook if created or not.

![alt text](image-12.png)

### Here we told sonarqube if jenkins is coming give something

### same we have to do with jenkins i.e. when sonar is coming give something

**Step 11:** install Maven

> repo link: https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/Maven.sh

**Step 12:** install Trivy

> repo link: https://github.com/saurabh-kumar-coder/Tools-installation-commands/blob/main/trivy.sh

So, here Trivy is a DevSecOps tool, the is used to validate images that are made.

Step 11: Interation of sonar into jenkins
![alt text](image-6.png)
![alt text](image-18.png)
![alt text](image-20.png)

**Step 13:** create a Docker hub account.
<br>

**Step 14:** Add docker credentials into jenkins.
![alt text](image-21.png)
![alt text](image-22.png)
![alt text](image-23.png)
![alt text](image-24.png)
![alt text](image-25.png)
![alt text](image-26.png)

**Step 15:** Add Jenkins Shared Library
![alt text](image-27.png)
![alt text](image-28.png)
![alt text](image-29.png)

**Step 16:** Go to pipeline in Jenkins
![alt text](image-30.png)
<br>
and run build
![alt text](image-31.png)
the build must fail as we have used the parameters but not given while running the build.
so, run it with parameters.
![alt text](image-32.png)

after this you can see the image is running into the docker container
![alt text](image-33.png)
