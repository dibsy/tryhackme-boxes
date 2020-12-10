```

PORT   STATE SERVICE VERSION                                                                                                                                                           
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))                                                                                                                                    
| http-methods:                                                                                                                                                                        
|_  Supported Methods: GET HEAD POST OPTIONS                                                                                                                                           
|_http-server-header: Apache/2.4.18 (Ubuntu)                                                                                                                                           
|_http-title: Apache2 Ubuntu Default Page: It works                                                                                                                                    
                                                       

PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 6d:2c:40:1b:6c:15:7c:fc:bf:9b:55:22:61:2a:56:fc (RSA)
|   256 ff:89:32:98:f4:77:9c:09:39:f5:af:4a:4f:08:d6:f5 (ECDSA)
|_  256 89:92:63:e7:1d:2b:3a:af:6c:f9:39:56:5b:55:7e:f9 (ED25519)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

~# gobuster dir -u http://10.10.65.99 -w /usr/share/wordlists/dirb/big.txt -x html,php,txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.10.65.99
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/dirb/big.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Extensions:     html,php,txt
[+] Timeout:        10s
===============================================================
2020/12/10 16:21:43 Starting gobuster
===============================================================
/.htaccess (Status: 403)
/.htaccess.txt (Status: 403)
/.htaccess.html (Status: 403)
/.htaccess.php (Status: 403)
/.htpasswd (Status: 403)
/.htpasswd.html (Status: 403)
/.htpasswd.php (Status: 403)
/.htpasswd.txt (Status: 403)
/administrator.php (Status: 200)
/index.html (Status: 200)
/server-status (Status: 403)
===============================================================
2020/12/10 16:21:50 Finished
===================================

```
