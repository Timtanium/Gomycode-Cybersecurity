# Checkpoint Intro To CyberSecurity
- First, I downloaded some VMs (virtualbox and vmware) for this checkpoint.

- Then I started by downloading the files I will use through a link provided in the platform and I made sure I saved them in the home directory with the username/password as follows (username:kali/password:kali)

- I started the kali, played with some basic kali commands; `cd, ls`.

I cd into the folder I downloaded my files into, 'Desktop',
I then used the 'ls' command to list the files in the folder 
![](image1/Capture.PNG)

- Cat command allows you to view the content of one or more files :

I used the command cat -n example.log example2.log to number the files.
![](image1/Capture%202.PNG)

>[!NOTE]
To find out the various functions of a command, call the command followed by a space and `--help`

![](image1/Capture%203.PNG)

- In order to save the output I used redirection to save the output inside a file :

cat -n example.log example2.log > access_log.log

I used the head command to show the first 10 lines: 
head access_log.log

I also used the tail command to show the last 10 lines: 
tail access_log.log
![](image1/Capture%205.PNG)

- To check the functions of the logger command, I used 'logger --help',
I then added information to the syslog located in /var/log/syslog by :
logger “This is Timmy”
![](image1/Capture%207.PNG)

- To check the functions of the grep command, I used 'grep --help'
![](image1/Capture%208.PNG)
I tried to use the Grep command to filter the output based on one value :
grep -i kali /var/log/syslog, and I got an error message saying I dont have syslog file
![](image1/Capture%209a.PNG)

So I installed syslog file by running the following commands
`sudo apt update` , `sudo apt install rsyslog` , `sudo systemctl enable rsyslog`, `sudo systemctl start rsyslog`. 
![](image1/Capture%209b.PNG)

![](image1/Capture%209c.PNG)

- I retried the Grep command to filter the output based on one value :
grep -i kali /var/log/syslog
![](image1/Capture%2010a.PNG)
![](image1/Capture%2010b.PNG)

- I filtered the log file for words containing p,l,c :
grep [plc] access_log.log
![](image1/Capture%2011.PNG)

I also filtered the output of the log for lines containing IP addresses:
grep -E "[^^][0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}" webserver.log
![](image1/Capture%2012.PNG)



#### The End Of Checkpoint 1