
1) install git and jenkins:
---------------------------

yum install git -y


amazon-linux-extras install epel -y


yum update -y

sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

sudo amazon-linux-extras install java-openjdk11

sudo yum install jenkins

systemctl start jenkins

systemctl jenkins status
____________________________________________________________________________________________________________________________________________________________


2) MAVEN:
---------

wget http://mirrors.estointernet.in/apache/maven/maven-3/3.8.5/binaries/

install maven integration plugin

and go to manage jenkins --> tools --> maven configuration

____________________________________________________________________________________________________________________________________________________________

3) install DOCKER:
------------------

steps:

      build @ push


yum install docker -y

systemctl start docker 

sudo chmod 666 /var/run/docker.sock

________________________________________________________________________________________________________________________________________________

4) sonarqube:
--------------

INSTALATION:

yum install java-1.8.0 -y

wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-6.7.6.zip


(server connect with database):
-------------------------------

yum install mysql -y 

mysql -h rds endpoind -u admin -P(port) -p (password)



PRE REQ:
========

=> 3 GB RAM

=> JAVA

=> Database

=>Create a user with permissions
     yum install mysql -y 
     mysql -h rds endpoind -u admin -P(port) -p (password)


=>Sonarqube Configuration file
    -wrapper.config
     java path ==> sudo update-alternatives --config java
    -(/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.402.b06-1.amzn2.0.1.x86_64/jre/bin/java)
    -sonar properties

=>modify the sonarqube owner permission
    -chowm -R ec2-user:ec2-user /opt/sonarqube-6.7.6/

=> We cannot start sonarqube as a root user
    ./sonar.sh start

go to install the plugin 
   -sonarqube scanner
go to configure and add the sonarqube instalations 
   -token--9284fc428f87f0ec12cf2d8913dd9e955ee858e3

 database :
 ----------   
  name     : sonar
  username : admin
  password : admin123


________________________________________________________________________________________________________________________________________________


5) NEXUS:
=========
http://qiita.com/leechungkyu/items/86cad0396cf95b3b6973


pre req:
---------

   ==> 3GB RAM 
   ==> JAVA (Nexus also depadent on java)
 
yum install java1.8.0

https://download.sonatype.com/nexus/3/nexus-3.66.0-02-unix.tar.gz

_________________________________________________________________________________________________________________________________________________________________________


