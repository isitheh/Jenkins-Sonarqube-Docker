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
  
### Jenkins - EC2 instance
1. Create Jenkins EC2 AWS Instance. [Ubuntu t2.medium]
2. chmod 400 "KEY-Jenkins.pem" in cmd/git where KEY-Jenkins.pem is.
3. ssh -i "KEY-Jenkins.pem" ubuntu@ec2-3-15-33-214.us-east-2.compute.amazonaws.com - terminal now 'ubuntu@jenkins:~$'
4. Check if Jenkins is intalled in EC2 instance: dpkg -l | grep jenkins then systemctl status jenkins then port sudo netstat -tulnp | grep 8080
5. Install Jenkins if not installed - sudo apt update then sudo apt install openjdk-11-jre
6. Now, copy the public IPv4 address of Jenkins
    - Public IPv4 address found in EC2 instance connect
    - Paste it into your browser, and put the port number 8080 after it [3.15.33.214:8080]
    - Login to Jenkins when prompted [isitheh, 01****]

### SonarQube - EC2 instance
1. Create SonarQube EC2 AWS Instance. [Ubuntu t2.medium]

### Docker - EC2 instance	

## Steps to cover
- Create three EC2 instances with a security group allowing traffic from the internet.
- Connect Jenkins instance to SonarQube, Docker instances through SSH (password-less connections w/ssh keys and IDs)
- Install SSH2 Easy plugin and set server
- Set server groups and server sites for Jenkins, SonarQube and Docker
- Create a Job on Jenkins with a git link for the repository with the branch to be built and deployed.
- Add steps in pipeline to configure the copying of code from Jenkins workspace to SonarQube and Docker instances for analysis and deployment.
