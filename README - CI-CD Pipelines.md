============================== Overview ==============================
CI/CD Pipeline Plan:
	- Push some code from user PC/IDE to the github repository
	- Pull the code from the repository into Jenkins server
	- Use the SonarQube server to do analysis on this code if its okay to deploy
	- When all SonarQube tests pass, deploy code to the Docker server.
	- End user will access the code from the Docker server.

============================== Jenkins ==============================
SSH into Jenkins EC2 AWS Instance.
1. On terminal navigate to downloads (or where ssh .pem file is stored).
2. ssh into jenkins instance using its public IP: ssh -i KEY-Jenkins.pem ubuntu@13.58.228.186 (13.58.228.186 - public_ipaddress - 4fca58eafe6d47028c2762e55b019311)
3. Make sure all permissions are set: chmod 400 KEY-Jenkins.pem then redo step 2 (if required)
4. When successful, on terminal prompt you should see the ubuntu@private_ipaddress
5. Type sudo apt update to update all jenkins instance dependencies
6. Install latest (for your Jenkins use) Java JDK or JRE: sudo apt install openjdk-17-jre (About 0.5GB space required)
7. Obtain the Ubuntu LTS release from Jenkins:
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
8. On the Jenkins instance, setup the inbound rules to allow port 8080.
9. Confirm the Jenkins continuous integration server status is running: systemctl status jenkins
10. Access the jenkins server from browser: public_ipaddress:8080 and login using secret key 4fca58eafe6d47028c2762e55b019311
	Secret key can be accessed on terminal using sudo cat /var/lib/jenkins/secrets/initialAdminPassword
11.	Login using admin/4fca58eafe6d47028c2762e55b019311
12. Create a user in Jenkins after loging in
13. Pull code from GitHub to Jenkins 	
============================== SonarQube ==============================

=============================== Docker ================================	