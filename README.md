# # Project Title
Deploying Java Application into Apache Tomcat and also generating SonarQube Report.
# Sample Image
![Project-2 (1)](https://user-images.githubusercontent.com/111736742/215831290-4456a2a1-5e63-4f17-a13d-5d614d04c59e.jpg)

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
```
## To deploy into Tomcat Server:

1) First install java on that server.
2) configure users in  conf/tomcat-users.xml
   under this #tomcat-users tag. 
```bash
<tomcat-users>
<user username="tomcat" password="12345" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
</tomcat-users>
```
