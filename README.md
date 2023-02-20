# # Project
Deploying Java Application into Apache Tomcat and also generating SonarQube Report.
# Sample Image

![project-1](https://user-images.githubusercontent.com/111736742/216734526-96c87bbb-2c9a-46f9-915a-7d8280538751.jpeg)

## SonarQube Report

To Generate SonarQube-Report: 
```bash
mvn sonar:sonar
  
```
 Configure SonarQube sever details in pom.xml:

 1-firstway(Password) 
```bash
 <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.7</maven.compiler.source>
    <maven.compiler.target>1.7</maven.compiler.target>
    <!-- <sonar.host.url>SonarQube Server url:Portnumber</sonar.host.url> -->
    <!--- <sonar.login>admin</sonar.login> -->
    <!--- <sonar.password>password</sonar.password> -->
 </properties>
  
```
2-Secondway(Token)
```bash
 <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.7</maven.compiler.source>
    <maven.compiler.target>1.7</maven.compiler.target>
    <!-- <sonar.host.url>SonarQube Server url:Portnumber</sonar.host.url> -->
    <!--- <sonar.login>SonarQube Token</sonar.login> -->  
 </properties>   
```
## To deploy into Tomcat Server:

## Installation

Install Apche-Tomcat

```bash
 # TO install java:
  yum install java-11* -y
 # TO install tomcat:
 cd /opt
 wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.71/bin/apache-tomcat-9.0.71.tar.gz
 tar -xvzf apache-tomcat-9.0.71
 mv apache-tomcat-9.0.71 tomcat
 #To start Tomcat
 cd tomcat
 cd bin
 sh startup.sh
 #To stop Tomcat
 cd tomcat
 cd bin
 sh shutdown.sh
 # To create softlink for startup.sh
 ln -s /opt/tomcat/bin/startup.sh /usr/bin/tomcatstart
 # To create softlink for shutdown.sh
 ln -s /opt/tomcat/bin/shutdown.sh /usr/bin/tomcatstop
```
configure users in  conf/tomcat-users.xml
   under this #tomcat-users tag. 
```bash
<tomcat-users>
<user username="tomcat" password="12345" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
</tomcat-users>
```
## Jenkins-dashboard
![test3](https://user-images.githubusercontent.com/111736742/220179478-046b21ed-3085-41a0-b81b-97b281b4161a.png)
## SonarQube-server
![test1](https://user-images.githubusercontent.com/111736742/220179592-233ed04d-ad47-4404-a4c8-e7d97f91a3e0.png)
## Nexus-server
![test2](https://user-images.githubusercontent.com/111736742/220179691-ba0b0754-e0cf-41a3-b6e0-a38a55e97d66.png)
## Deployment-Approval
![test6](https://user-images.githubusercontent.com/111736742/220179734-85e53543-01c4-4848-b473-471cac2aa397.png)
## Tomcat-Deploy
![test5](https://user-images.githubusercontent.com/111736742/220179794-ade72b0f-0a3e-4657-b81e-3dd84326909f.png)



