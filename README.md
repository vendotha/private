WIRESHARK
1. sudo apt install wireshark (if its not already installed)
2. sudo wireshark
3. choose 'any' for interface
4. open 'mvsrec.edu.in' in any browser
5. now go to wireshark and click on 'stop capture' (its a red square on top left)
6. in the 'apply a display filter...' field, type 'tcp contains mvsrec' (without the quotes) and press enter/click on find
 (if this isnt working, click on the magnifying glass icon, change the 'display filter' drop down to 'string' and type 'mvsrec' there in the textbox
7. you can now find mvsrec.edu.in in the encrypted texts place (bottom part of wireshark with all 00 11 aa etc) 
  (you wont immediately find it, search patiently)

8. now for showing ssh traffic in wireshark
  go to a new terminal(not the wireshark one) and type 
  -> sudo apt-get install openssh-server

9. after installation, type
	-> sudo systemctl start ssh
	-> sudo systemctl status ssh
        -> sudo adduser sshuser (here you set up a password, set up 'mvsr' as password, if it asks other stuff like full name, room number and stuff, just Ctrl+C and leave that command)
        
10. now go to wireshark application and start capture again (shark icon in top left corner)

11. go back to the ssh terminal and typ
  -> ssh sshuser@127.0.0.1
 (wait 15 seconds)
   -> exit

12. go to wireshark and type 'ssh' in the display filter place
you will see all ssh traffic, show the madam that it is 'encrypted packet' everywhere, thats the whole point of ssh.

STEG

1. go to google and download any jpeg image
2. save it as picture.jpeg in Downloads folder
3. go to Downloads folder and create a 'demo.txt' file here, give some data in it and close
3. open terminal in the downloads folder only
5. check is steghide is present by typing 
	-> which steghide
if its not there
	-> sudo apt -get install steghide
6. -> steghide embed -ef demo.txt -cf picture.jpeg
enter the password for kali
7. now go to the downloads folder and delete the 'demo.txt' file
8. back to terminal
   -> steghide extract -sf picture.jpeg
9. see in the downloads folder again, demo.txt will be back with the same data you gave before
enjoy

SOCIALPHISH
(in terminal)
1. -> cd Desktop
2. go to browser and type 'socialphish github', you'll get some github link open it and copy the url
3. (back to terminal)
   -> git clone (paste the url you copied)
   -> ls (you'll find the dir. name that gitclone created it'll usually be socialphish only, put that in next step)
   -> cd socialphish
   -> ls (you'll find the .sh file put that in next step)
   -> chmod +x socialphish.sh
   -> ./socialphish.sh
4. choose an option, example 01 for instagram
5. navigate to the localhost website that it gives and type some dummy username and password (dont give real)
6. the same you typed will be displayed in terminal

NMAP
1. installation
-> sudo apt install nmap

TCP SYN Scan (Stealth Scan)  
-> sudo nmap -sS scanme.nmap.org

TCP Connect Scan
-> sudo nmap -sT scanme.nmap.org

TCP FIN Scan
-> sudo nmap -sF scanme.nmap.org

Xmas Scan
-> sudo nmap -sX scanme.nmap.org

Null Scan
-> sudo nmap -sN scanme.nmap.org

each output you should get some port state service
if you get 'not connecting' etc then error

HARVESTER

-> theHarvester -d mvsrec.edu.in -l 200 -b bing

it will give output, it will show 2 hosts identified
data.mvsrec.edu.in
results.mvsrec.edu.in

WHOIS
go to website    whois.com/whois
type any website name, example mvsrec.edu.in, you will get alllll data about mvsr website show them

NETCRAFT
go to website  sitereport.netcraft.com
type any website name, example mvsrec.edu.in, you will get alllll data about mvsr website show them

DNS
go to website  dnsdumpster.com
type any website name, example mvsrec.edu.in, you will get alllll data about mvsr website show them

