### CI-CD Pipeline From Scratch
============================== Overview ==============================
CI/CD Pipeline Plan:
	- Push some code from user PC/IDE to the github repository
	- Pull the code from the repository into Jenkins server
	- Use the SonarQube server to do analysis on this code if its okay to deploy
	- When all SonarQube tests pass, deploy code to the Docker server.
	- End user will access the code from the Docker server.
============================== Jenkins ==============================
1. Create Jenkins EC2 AWS Instance. [Ubuntu t2.medium]
2.  	
============================== SonarQube ==============================
1. Create SonarQube EC2 AWS Instance. [Ubuntu t2.medium]
2. 
=============================== Docker ================================	
