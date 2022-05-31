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

created a new git branch for the jenkinspipline-stages

![](images/11.png)

![](images/12.png)

added test stage script in jenkins file under the branch to trigger a build

![](images\jenkinsfiletest.png)

Pushed chnages from new branch to main branch

![](images/13.png)

![](images/14.png)

![](images/15.png)

![](images/16.png)


Added 3 stages - package, deploy, clean up

![](images/jenkinsfilestages.png)

![](images/jenkinsfilestages1.png)

Updated git repo to initiate build

![](images/17.png)

pushed changes from new branch to main 

![](images/18.png)

![](images/19.png)

## Configuring ansible on jenkins server

Installed ansible and its dependencies on jenkins server

![](images/20.png)

Installed ansible plugin on jenkins ui

![](images/23.png)

![](images/24.png)

![](images/25.png)

![](images/26.png)

![](images/27.png)

![](images/28.png)

Added new scripts to jenkinsfile

![](images\jfileinit.png)

![](images\jfile.png)

![](images\30.png)

Updated ansible.cfg with the necessary configurations

![](images/22.png)

Updated necessary environments in the inventory directory

![](images/21.png)

![](images\31.png)

installed and configured postgresql and nginx role from ansible galaxy

![](images/33.png)

updated the ansible playbooks/site.yml and static-assignments file

![](images/32.png)

![](images/dbyaml.png)

![](images/nginxyaml.png)

Pushed changes to git repo and merged with main

![](images/34.png)

![](images/35.png)

![](images/36.png)

![](images/37.png)

![](images/38.png)

![](images/39.png)

Introduced parametization in jenkinsfile so the different env's can be executed without needing to manually change and update the

![](images/40.png)

![](images/para.png)

![](images/41.png)

![](images/42.png)

![](images/43.png)




## ci/cd pipeline for todo application

cloned https://github.com/ladifa1/php-todo.git repo

Installed php, its dependencies and composer tool on jenkins server

![](images/44.png)

![](images/45.png)

![](images/46.png)

![](images/47.png)


Installed ansible artifactory role

Installed plot plugin and artifactory plugin on jenkins ui

![](images/48.png)

Configure artifactory on jenkins ui

![](images/55.png)


Created new jenkins file on todo repo

![](images/pipline1.png)

![](images/pipline2.png)

![](images/pipline3.png)

![](images/pipline5.png)

![](images/pipline6.png)

![](images/pipline7.png)

Configure inevntory file, playbooks and static-assignments

![](images/49.png)

![](images/50.png)

![](images/51.png)

Created multibranch pipeline on blue ocean and run build on CI

![](images/52.png)

![](images/53.png)

open artifactory url

![](images/54.png)

Created database and database user on db server

![](images/56.png)

![](images/59.png)

![](images/60.png)

![](images/61.png)

![](images/62.png)

![](images/63.png)


Updated jenkinsfile with pipeline config

![](images/64.png)

Run php-todo build 

![](images/65.png)

Install phploc

![](images/66.png)

![](images/67.png)


Updating jenkinsfile, static-assignments, playbook and builds

![](images/68.png)

![](images/69.png)

![](images/70.png)

![](images/72.png)

![](images/74.png)

![](images/75.png)

![](images/76.png)

![](images/77.png)

![](images/78.png)

![](images/79.png)

![](images/80.png)

![](images/81.png)

![](images/82.png)

## sonarqube 

installed sonarqube

Updated inventory, playbooks and static-assignments

installed java

installed postgresql db for sonarqube

configured sonarqube and open port 9000

![](images/83.png)

![](images/84.png)

![](images/85.png)

![](images/86.png)

![](images/87.png)

![](images/88.png)

![](images/94.png)

![](images/code.png)

## Configure slave user on jenkins

installed java on slave

updated bash profile with java

configured slave node on jenkins

configured github webhook trigger

![](images/91.png)

![](images/92.png)

![](images/93.png)

![](images/95.png)

![](images/96.png)
