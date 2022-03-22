Clone the repository.

Run "docker compose up -d" to build and run all containers. 

Open docker desktop to start shell sessions in any container. 

Use container curl_instance to send exploit payload. User container c2_instance to recieve reverse shell on port 9999.

Exploit payloads must be sent using IPs, not hostnames. Use 'ping -c 1 <container_hostname>' in curl_instance to get the IP of any container. Hostnames are:
1. web_server
2. http_server
3. ldap_server


