# CI-CD: Jenkins-Sonarqube-Docker
============================== Overview ==============================

Repository where I upload my ci-cd dev projects and supporting files.

Following tutorial: https://chirag0002.hashnode.dev/build-a-cicd-pipeline-using-jenkins-sonarqube-docker-and-aws

======================================================================
## CI/CD Pipeline Plan:
- Push some code from user PC/IDE to the github repository
- Pull the code from the repository into Jenkins server
- Use the SonarQube server to do analysis on this code if its okay to deploy
- When all SonarQube tests pass, deploy code to the Docker server.
- End user will access the code from the Docker server.
  
### Jenkins
1. Create Jenkins EC2 AWS Instance. [Ubuntu t2.medium] 

### SonarQube
1. Create SonarQube EC2 AWS Instance. [Ubuntu t2.medium]

### Docker	

## Steps to cover
- Create three EC2 instances with a security group allowing traffic from the internet.
- Connect Jenkins instance to SonarQube, Docker instances through SSH (password-less connections w/ssh keys and IDs)
- Install SSH2 Easy plugin and set server
- Set server groups and server sites for Jenkins, SonarQube and Docker
- Create a Job on Jenkins with a git link for the repository with the branch to be built and deployed.
- Add steps in pipeline to configure the copying of code from Jenkins workspace to SonarQube and Docker instances for analysis and deployment.
