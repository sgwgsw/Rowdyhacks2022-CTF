This repo is to be used for educational purposes only, and is intended to be run against your own machine. We do not condone the use of these skills/techniques outside of this lab environment. DO NOT change any files or commands; run exactly as described in “Starting the Lab” steps 1-4.  



**Scenario**

A local kitten daycare has recently suffered a zero-day exploit resulting in full system compromise via RCE (remote code execution). A digital forensics team investigating the incident has created a LAB environment meant to serve as a proof-of-concept for what happened. Can you replicate what happened that fateful day for the local kitten daycare?



**Pre-Requisites**
1.    Docker Desktop – https://www.docker.com/products/docker-desktop/ 
2.    Git – https://git-scm.com/book/en/v2/Getting-Started-Installing-Git 



**Starting the Lab Environment**

** Be sure to run the below commands with administrative/root privileges (e.g. 'sudo docker compose up -d').
1.    Open Docker Desktop
2.    Run 'git clone https://github.com/sgwgsw/Rowdyhacks2022-CTF.git' in a terminal window.
3.    Change to the Log4j_LAB-Docker folder and run 'docker compose up -d' with admin/sudo privileges.
4.    Once the command has finished running, select 'Containers / Apps' in Docker Desktop to confirm all containers in the stack are running


**Hints**

1.    To start a Docker CLI session, hover over the container in 'Containers / Apps' on Docker Desktop and click the 'CLI' button. DO NOT open CLI sessions by other means. 
2.    You will not need a CLI session on web_server (remember - this would be the victim's web server which we are trying to hack. An attacker wouldn't have access to this system).  
3.    Use 'ping -c 1 <container_hostname>' to get the IP of any container. Hostnames are: web_server, http_server, ldap_server, c2_instance, curl_instance
4.    The web_server container is running a Tomcat web server instance 8080. Log4j 2.14.0 is in-use.
5.    The curl_instance container will be useful for sending the exploit.
6.    The c2_instance container has netcact. 
7.    The ldap_server container is hosting the reference object, 'Exploit'.
8.    The http_server container is hosting compiled java code. This code wants to communicate on port 9999. 



**WHEN YOU ARE FINISHED**
1.    Close any CLI/terminal sessions
2.    Click the stop button in 'Containers / Apps' on Docker Desktop
3.    Run 'docker system prune -a' on the host machine, and press 'y' when prompted
4.    Delete the cloned Log4j_LAB-Docker repo/folder on your machine
