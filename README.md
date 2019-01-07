# DevOps-Test

Step1: Created EC2 Machines in AWS
MSR-test-Instance-1
Public IP: 18.206.154.55

MSR-test-Instance-2
Public IP: 3.83.22.181

Created a user ansible in both machines and my local machine.
created shh key for ansible user. 
Copied the ssh public key to both the EC2 machine's Authorized_keys to enable password less authentication for Ansible 

Step2: Installed required software using Ansible
*command: ansible-playbook Install_Softwares.yml

Step3: Created Docker container for apache webserver using below in MSR-test-Instance-1
/webapp/Dockerfile
/webapp/index.html
docker-compose.yml
*command: sudo docker-compose up -d

Step4: Created Docker container for CouchDB using below in MSR-test-Instance-2
CouchDB/docker-compose.yml
*command: sudo docker-compose up -d

Step5: Using ansible to run docker-compose file in EC2 machines
*command: ansible-playbook ansible-docker.yml


To access Apache webserver
http://18.206.154.55:8080/

To access CouchDB futon 
http://3.83.22.181:9980/
