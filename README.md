I start by running "sudo openvpn PwnTillDawn.ovpn" after opening terminal under the downloads folder where the OpenVPN file is located.

Then, I ran the nmap scan using "nmap -sC -sV -Pn 10.150.150.11"

I continued by running the gobuster program with "gobuster dir -u http://10.150.150.11/ -w /usr/share/wordlists/dirb/common.txt"

Once "/Admin" was found, I used firefox to browse the IP adress to access the admin page, where I created a new user with elevated access.

After creating an admin account, I uploaded the cmd.php web shell payload via the admin dashboard. This allows me to receive a username return, followed by gaining Remote Code Execution (RCE).

In the address bar, I navigated through the directory via "?cmd=type C:\Users\Administrator\Desktop\FLAG1.txt". After receiving the flag's value, I proceeded to input "PwnTillDawnAcademyIsAwesome!" into the flag submission on the main PwnTillDawn page.

Finally, the page displays the completion certification, indicating that the system was succesfully compromised.
