# CONTINUOUS INTEGRATION WITH JENKINS  ANSIBLE  ARTIFACTORY  SONARQUBE  PHP

## Set up enviroments for ci/cd pipeline

installing necessary applications and dependencies on jenkins, nginx, database and tooling servers.

Create redhat ec2 instance

configure instance

`sudo dnf install wget -y`

![](images/1.png)

`sudo dnf install -y java-11-openjdk-devel`

![](images/2.png)

`java -version` 

![](images/3.png)

`sudo alternatives --config java`

![](images/5.png)

`sudo dnf install -y jenkins`

![](images/4.png)

`sudo systemctl start jenkins`

`sudo systemctl enable jenkins`

`sudoo systemctl status jenkins`

Set up jenkins 

![](images/6.png)

Create a folder deploy in ansible config repo and create a jenkinsfile with below configurations

![](images/8.png)

Set up jenkins and add the jenkinsfile to the build configuration

Run build 

![](images/9.png)

Set up blue ocean ui on jenkins

![](images/10.png)