# Writeup 2 - OSINT

Name: Michael Lin
Section: 0201

I pledge on my honor that I have not given or received any unauthorized assistance on this assignment or examniation.

Digital acknowledgement: Michael Lin

## Assignment Writeup

### Part 1 (45 pts)

`v0idcache`'s real name is Elizabeth Moffet. Her website is http://1337bank.money/. Her email address is v0idcache@protonmail.com. I found her email address on her website. I discovered this by looking up 'voidcache' on twitter. Her followers is UMD CyberSecurityClub. I also found her website because it was in her twitter link. Based on her twitter profile she is a Banking CEO from the Neatherlands and one of her friends is Dev0id_cache who's twitter name is @CacheDev0id. Her favorite food is Chop suey from her twitter. 

The IP address associated with the website is 142.93.136.81. The location of the server, any history in DNS is Geolocation: CA (Canada), ON, Ontario, M5B Toronto. I found this out from searching up the history of the DNS. https://securitytrails.com/domain/1337bank.money/dns. 

By doing nmap -v -A http://1337bank.money/, I found a hidden file was on Port 80 which had an unnamed git repository and I found a hidden file called robots.txt and COMMIT_EDITMSG. I found the flag h1d3_s3cret_glts using the same nmap -v -A http://1337bank.money/ because it was in a commit message. I found another flag called h1dd3n_1n_plain_5ight by going to view source on their website. 

I discovered port 80/tcp, port 22/tcp, 1337/tcp, are open ports. On port 22, the service is SSH. On port 80, the service is HTTP. On port 1337, it's HTTP. I discovered this by running on nmap -v -A http://1337bank.money/ which listed out open ports on the website in the kali linux. 

The operating system I discovered on the website is Ubuntu 4 Linux. I discovered this by doing nmap -v -A http://1337bank.money/ which also listed out the OS on the port 22. 

Afterwards, I went on http://1337bank.money/robots.txt because I knew that was a hidden file and it showed me a directory called secret_directory. I went on http://1337bank.money/secret_directory and found the flag {h1ding_fil3s_in_r0bots_L0L}. 
	
### Part 2 (75 pts)

I used the hostname from the IP address and found it to be v0idcache. I then wrote the stub.py program to read through every single line in the robox.txt sending the username and then getting a response for that username, and then sending the password and then getting a response from the password and then getting a final response on whether it failed or not. I used an if statement on if the final response wasn't a Fail or an empty string or a new line then it must be the right password and I printed it. Once I had the password which was linkinpark, all I had to do was login and try to find the flag file. To find the flag file, I had to use grep and the file name. grep -i -r "FLAG". 

The flag was in home/flag.txt:Good work! Here's a flag: CMSC389R-{brut3_f0rce_m4ster}. 
