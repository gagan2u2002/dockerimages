# dockerimage's
Different Docker(s) images i have put on this and this will help to make your environment using docker.

i have setup docker on my box  10 Box by installing docker toolBox . Docker Toolbox avaliable for window 10 plateform.
For setup purpose you can use below url-
https://store.docker.com/editions/community/docker-ce-desktop-windows

If you want to look docker documnetation you can follow below link , there is a good documentation provided by Docker Team
https://docs.docker.com/docker-for-windows/


# Docker Instruction for making My-SQL environment on Window Box/machine

STEP 1: docker load -i mysqlImage.tar  

STEP 2: docker tag <image id> centos/mysql-56-centos7
  
STEP 3: docker run -d --name mysql_database -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_ROOT_PASSWORD=pass -e MYSQL_DATABASE=db -p 3306:3306 centos/mysql-56-centos7

or 
   you can run STEP 3 directly on command prompt skip STEP 1 and STEP 2 as these steps are for installing mysqlImage.tar 
   
   * For installing Mysql 5.7 version on centOS use below command                
   docker run -d --name mysql_database -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_ROOT_PASSWORD=pass -e MYSQL_DATABASE=db -p 3306:3306 centos/mysql-57-centos7

*Where <image id> is the id of the loaded image from first command.
Executing above commands will run an instance of mysql in docker container at port 3306.
  
*When you  installed image below is the output you can view on command prompt or docker cli 

C:\Users\gagan>docker load -i "C:\Users\gagan\OneDrive\Desktop\IOM\mydockersimages.tar"
dc1e2dcdc7b6: Loading layer [==================================================>]  200.2MB/200.2MB
45cef955d7d0: Loading layer [==================================================>]  181.3MB/181.3MB
e4581fb96897: Loading layer [==================================================>]  65.54kB/65.54kB
cea8c37b28af: Loading layer [==================================================>]   2.56kB/2.56kB
83c164d0524e: Loading layer [==================================================>]  8.192kB/8.192kB
ee4c6e99c71f: Loading layer [==================================================>]  9.216kB/9.216kB
Loaded image ID: sha256:ded746533e057dba6ab5a876208a1d7768a89f19356dce3fc656e2e386647bca

C:\Users\gagan>docker tag sha256:ded746533e057dba6ab5a876208a1d7768a89f19356dce3fc656e2e386647bca centos/mysql-56-centos7

C:\Users\gagan>docker run -d --name mysql_database -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_ROOT_PASSWORD=pass -e MYSQL_DATABASE=db -p 3306:3306 centos/mysql-56-centos7
b62920551a4d356bef21a775a30b21b2d5c30e50b93e6c0a8c2d1a38bde67bc5


C:\Users\gagan>docker ps -a
CONTAINER ID        IMAGE                     COMMAND                  CREATED             STATUS              PORTS                    NAMES
b62920551a4d        centos/mysql-56-centos7   "container-entrypoin…"   15 seconds ago      Up 13 seconds       0.0.0.0:3306->3306/tcp   mysql_database
b62920551a4d1        centos/mysql-56-centos7   "container-entrypoin…"   15 seconds ago      Up 13 seconds       0.0.0.0:3306->3306/tcp   mysql_database


