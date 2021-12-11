Software installed:

1. Java -> openjdk 11.0.11 
2. Jenkins -> version 2.319.1
3. Git -> version 2.25.1
4. Docker CE -> version 20.10.11

Note: All setup has been done on AWS EC2 Ubuntu instance.

Prerequisites:

1. Java should installed and setup Java variables
2. Jenkins should be installed (with all the required plugin installed), up and running  
Note: we are running this jenkins service on port 8081 and port 8080 will be bind with the resultant service.  
3. Git should be installed and configured with Jenkins
4. Docker should be installed, up and running

Steps:

1. Create Dockerfile to create jenkins container with latest available base image and expected plugins(Golden Image).
Note: No roles has been created as of now

Solution: 
1. We installed required plugins using Dockerfile and then launched jenkins. Setup all the roles manually on Jenkins through jenkins configuration.
2. That can be achieved by creating separate YAML file that will be called in Dockerfile.

3. Create Git hub repository and docker hub repositry for uploading all the required files and stroing images respectively
4. Push all the necessary files on github repository.
5. Configure Jenking with dockerhub credentials.
6. Create Jenkisfile to perform step 2 given in assignement that will automate and publish the jenkins image with all the plugins installed (Golden Image) as stated in step 1
Note: No test cases has been written.
Solution: Test cases can be written as a separate Stage in Jenkins pipeline

7. Jenkins pipeline then can be build that will result in creating a container hosting Jenkins service (created using Golden Image). Jenkins service will be up and running on port 8080


Links:

https://github.com/pathania25/csassignment.git
https://hub.docker.com/repository/docker/pathania90

Jenkins Url: http://3.80.147.9:8080/
