## Project on shell scripting.
### Using Shell script commands, we can see complete info of Users and System.
- Create a file names as ```script.sh``` and it will open automatically.
- Press ```'i'``` to write on this file i.e insert mode
> ### Note: Try to write everything in editor for better understand
#### Code:
~~~
#!/bin/bash
echo "~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~"
echo ""
echo "You are Welcome $1 - You are currently in $HOME"
echo""
echo "-------------------------------------------------------------"
echo ""
echo "Today is $(date | awk '{print $1,$2,$3}') and the time is $(date | awk '{print $4,$5}')"
echo ""
echo "============================================================="
echo ""
echo "The Uptime of system is:-"
echo "$(uptime)"
echo "You are currently using:- $(who -H | xargs | awk '{print $5}')"
echo""
echo "Last logins:"
last -a | head -3
echo ""
echo "----------------------------------------------------------"
echo ""
echo "Last logged-in at:- $(uptime | xargs | awk '{print $1}') since $(uptime | xargs | awk '{print $3}') hours"
echo "============================================================="
echo ""
echo "Free Disk Space on your system:- $(df -H | xargs | awk '{print "Free Space/Total Disk Space: "$10"/"$9}')"
echo "-------------------------------------------------------------"
echo ""
echo "Free RAM available in system:- $(free -h | xargs | awk '{print "Free Memory/Total Memory: " $10"/"$13}')"
echo "============================================================="
echo ""
top -b | head -3
~~~
- Press ```Esc``` key to exit insert mode
- Then type ```:wq``` or ```:x``` to save and exit from vim editor
- Now by using ls -la we can see this file is permitted to read for everyone, write for owner and no execution for anyone.
- Change the permission by giving command ```chmod 700 script.sh``` & check by ```ls -la```
- Now for execution, we use ```./script.sh``` or ```bash script.sh```
> ### Make sure you are in current directory path to execute this script.

#### OutPut for this concept looks like this:
![1](https://user-images.githubusercontent.com/116208380/211182918-798b508f-2112-4b21-886f-e1b217670153.jpg)

#### Amazing concept of this project's credit goes to [rohit chavhan](https://github.com/rohit-chavan-2151)

#### Happy to learn this!!
