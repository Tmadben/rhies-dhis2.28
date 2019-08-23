# rhies-dhis2.28
This document describe how to install and run DHIS2.28 using docker containers in the case of RHIES project. 

# Prerequisites
 - Be RHIES project member.
 - Have a docker hub account
 - Get the pull permission on SAVICS organisation repositories on docker hub.
 - Have internet connection
 - Have docker installed

# Components
 ### 1. Tomcat 7 with jdk8 image
 We use tomcat:7jdk8 image as a base image (FROM tomcat:7jdk8) to build our customized tomcat.
 The new built image contains the dhis.conf file, the hibernate.properties file and dhis.war file.
 This new tomcat image is available at "savicsorg/dhis2-tomcat7jdk8" repository on docker hub.
 
 ## 2. Postgresql 9.5.19
 We also use postgres:9.5.19 as a base image to build our customize database server. The final image contains some init scripts to create the new database and to create the default user. We also add one dhis2 database dump file to populate our new database.
 It is available at "savicsorg/dhis2-postgresql9.5" repo on docker hub.
 
 # How to run DHIS2.28
  1. In command line connect to docker hub with your account login and password:\
  -- $ docker login 
  2. Create one file with docker-compose.yml as a name. Copy and paste into this file, the content of my docker-compose.yml:\
  -- $ nano docker-compose.yml
  3. The last thing, run the containers. Your have to run it where your docker-compose file is:\
  -- $ docker-compose up.
  4. Connect to your dhis2 with your browser when all the server are started. The default port is 8082 that you could change in the docker-compose.yml file:\
  -- http://yourIPaddress:8082
