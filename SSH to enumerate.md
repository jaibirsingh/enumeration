# SSH -basics

* Q1. What is the version of SSH server.
  * Answer: Command: nmap -sV 192.201.39.3

* Q2. Fetch the banner using netcat and check the version of SSH server.
  * Answer: Command: nc 192.201.39.3
 
* Q3. Fetch pre-login SSH banner.
  * Answer: Command: ssh root@192.201.39.3

* Q4. How many “encryption_algorithms” are supported by the SSH server.
 * Answer: Command: nmap --script ssh2-enum-algos 192.201.39.3


* Q5. What is the ssh-rsa host key being used by the SSH server.
  * Answer: Command: nmap --script ssh-hostkey --script-args ssh_hostkey=full 192.201.39.3

* Q6. Which authentication method is being used by the SSH server for user “student”.
  * Answer: Command: nmap -p 22 --script ssh-auth-methods --script-args="ssh.user=student" 192.201.39.3
 

* Q7. Which authentication method is being used by the SSH server for user “admin”.
  * Answer: publickey, password
  * Command: nmap -p 22 --script ssh-auth-methods --script-args="ssh.user=admin" 192.201.39.3
 

* Q8. Fetch the flag from /home/student/FLAG by using nmap ssh-run script.
  * Answer: Command: nmap -p 22 --script=ssh-run --script-args="ssh-run.cmd=cat /home/student/FLAG,ssh-run.username=student,ssh-run.password=" 192.201.39.3
 
