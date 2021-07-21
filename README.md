# linux-command

Linux basic commands

#pwd 	-It will print the working directory
#locate	-It will show us the location of a file we enter
#ls     	-It will list the contents of the particular directory
#cd     	-It will change the directory
#mkdir	-It will make the new directory
#rmdir	-It will remove the directory
#rm   	-It will remove the file
#rev	-It will reverse the each word and character
#cal	-It will used to view the calander also we can view specific month and year
#fortune	-It will show us some funny phrase with some comics
#wget	-It will download files from the web right from terminal
#lsblk  	-It will show the available block devices
#uname	-It will shows the system information
#which 	-It will used to search the executable files
#service	-It will used to run systems function in terminal like network-manager
#shutdown-It will shutdown the devices
#history	-It will show us the history of commands we used
#clear	-It will clear the terminal
#echo	-It will used to print the text u entered
#sudo	-It used to access root like stuffs
#man	-It used to view the manual of the command
#alias	-It used as an shortcut for long commands or commands like $ alias CD="cd /etc"
#unalias	-It used to unalias the alias command
#less	-It used to view the contents of the file
#whatis	-It used to get manual page discriptions
#ln  	-It is used to create link between files
#comm	-It compare two files for common and distinct lines
#cmp	-It compares and show differ as bytes
#rsync	-It used to sync two directories using ($rsync -zvr) in the local computer
#sysctl	-It used to view and modify kernel parameters at runtime.
#mount 	-it will mount the filesystem with your external devices like pendrive
#nmap 	-It will used to check the network availability,which device is active like stuffs.
#iptables 	-It act as an firewall it controls the incoming and outgoing packets or traffic.
#df        	-it provides essential information about the disk space
#free	-It will show the freespace and total memory like stuffs
#ps        	-it will show what process is running currently
#kill      	-it will stop the process (# kill -9 31186 31187)
#cat 	-concatinate multiple files, create new file, show the file with number by using n
#head	-It used to show the first 10 lines of the file
	  $ head -n 5 state.txt it shows first 5 lines
#tail         	-It prints last 10 lines of the file
	  $ tail -n 3 state.txt it shows last 3 lines
#diff     	-it shows the differene with some symbol like a-add, c-change, d-delete (1c1)(1,2d1,2) here number describes the line
#awk	-it can search the text in the file(awk '/hari/' harie.txt)
	 it can find largest and smallest number (awk '$1 >200' employee.txt) where $1 describes the first coloumn
	 it can use if else
#netstat  	-it used to see the network status and all (# netstat -a | more, # netstat -ap | grep ssh, # netstat  a)
#chmod 	-It gives and changes the permission like user can access it,read it, write it, execute it
	 (chmod u+x filename) u is for user,g is for group,and o is for others - r is for read permission,
	 w is for write permission, x is for execute permission.
	 chmod -R 755 directory-name/ R is used to change the permission recursively
#find         -It finds the file (# find -iname "MyCProgram.c"),  $find /home -user root
	 it can execute by finding ($ find -iname "MyCProgram.c" -exec md5sum {} \;)
	 Find all empty files in home directory (# find ~ -empty)
#grep         -It used to search the text in a file Search for a given string in a file ($ grep -i "the" demo_file)
	  Print the matched line, along with the 3 lines after it ($ grep -A 3 -i "example" demo_text)
	  Search for a given string in all files recursively($ grep -r "ramesh" *)
#crontab 	 -It used to run the file in the background at specific time every day
	  Run at 12:01 a.m. 1 minute after midnight everyday. This is a good time to run backup when the system is not under load.(1 0 * * * /root/bin/backup.sh)
	  Run backup every weekday (Mon – Fri) at 11:59 p.m. (59 11 * * 1,2,3,4,5 /root/bin/backup.sh)
#sed         -It used to remove the letter in a lastword of each line ($sed 's/.$//' filename)
	Print file content in reverse order ($ sed -n '1!G;h;$p' thegeekstuff.txt)
	Add line number for all non-empty-lines in a file ($ sed '/./=' thegeekstuff.txt | sed 'N; s/\n/ /')
	Eliminate Comments Using sed Delete all the comment lines from a file as shown below using sed command.
	($  sed -e 's/#.*//' thegeekstuff.txt)
#cut          -It used to cut the certain column and display what we eneterd ($ cut -d: -f 1 names.txt)
#curl 	It used to save the output of the file especially URL
	Save the cURL Output to a file: $ curl -o mygettext.html http://www.gnu.org/software/gettext/manual/gettext.html
#ifconfig  -Display Details of All interfaces Including Disabled Interfaces # ifconfig -a
	Disable an Interface # ifconfig eth0 down
	Enable an Interface # ifconfig eth0 up
	Assign 192.168.2.2 as the IP address for the interface eth0. # ifconfig eth0 192.168.2.2
	Change Subnet mask of the interface eth0. # ifconfig eth0 netmask 255.255.255.0
	Change Broadcast address of the interface eth0. # ifconfig eth0 broadcast 192.168.2.255
	Assign ip-address, netmask and broadcast at the same time to interface eht0.
	# ifconfig eth0 192.168.2.2 netmask 255.255.255.0 broadcast 192.168.2.255
#tar          -It will craete an single archive backup file (# tar cvf /tmp/my_home_directory.tar /home/jsmith)
#lsof        -It will list the open files
#sort        -It will sort in asscending order #sort hari.txt
	desc #sort -r  hari.txt
#Xargs     -Copy all images to external hard-drive # ls *.jpg | xargs -n1 -i cp {} /external-hard-drive/directory
	Search all jpg images in the system and archive it. # find / -name *.jpg -type f -print | xargs tar -cvzf images.tar.gz
	Download all the URLs mentioned in the url-list.txt file # cat url-list.txt | xargs wget –c
---------------------------------------------------------------------------------------------------------------------------------------------
Create a user
	*Add a new user – Basic method Specify only the user name. # useradd jsmith
	*-c : Description about the user.
	  -e : expiry date of the user in mm/dd/yy format
	   # adduser -c "John Smith - Oracle Developer" -e 12/31/09
	*Change the user password # passwd jsmith
Create a group
	*Create a new developer group # groupadd developers
	*Add an user to an existing group # usermod -g developers jsmith
	*Validate the users group was modified successfully # grep jsmith /etc/passwd
