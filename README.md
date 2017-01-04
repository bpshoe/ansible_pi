loginto pi at keyboard
enable the SSH server via raspi-config (advanced options>SSH) or your preferred method
make sure you can successfully SSH from the ansible machine using pi/raspberry

Run it:

ansible-playbook -i scrollpi.bpshoe.com, -k main.yml

Parameters: 
	SSH Password: this is the password for the pi. By default it is 'raspberry'.
	Hostname: new hostname for the raspberry pi, use alpa numeric characters.
	Username: enter the username of the new user that ansible will create. 
	Password: enter salted pass for the new user (openssl passwd -salt <salt> -1 <plaintext>).



ansible-playbook -i scrollpi.bpshoe.com, -k cleanup.yml

I used the page below as a guide for what should be done. In addition to the current configuration a firewall would be also help with security but that more depends on the usecase for the server. 
https://mattwilcox.net/web-development/setting-up-a-secure-home-web-server-with-raspberry-pi

Fail2ban will keep brute force attacks at bay, but keep in mind this setup is only as secure as the password for your new user. 