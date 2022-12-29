```bash
gcloud compute instances create sonarqubeserver --zone=us-west4-b --machine-type=e2-medium --create-disk=auto-delete=yes,boot=yes,device-name=sonar,image=projects/centos-cloud/global/images/centos-7-v20221206,mode=rw,size=20
```
## Oracle Java Installation

```bash
#Login as a root user
sudo su -

##Change dir to /opt
cd /opt
yum install wget -y
wget -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.rpm
yum install jdk-8u131-linux-x64.rpm -y

java -version

 
```

## install sonarqube
```bash
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.8.zip
unzip sonarqube-7.8.zip
useradd sonar
chown -R sonar:sonar /opt/sonarqube-7.8/
chmod 755 /opt/sonarqube-7.8/
# switch user to sonar
su - sonar
cd /opt/sonarque-7.8
cd bin
sh sonar.sh start
sh sonar.sh status
# Once the installation is done, access the sonarqube at 9000 port. 
admin/admin
```
