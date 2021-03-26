# L I N U X - <img src="https://www.showmetech.com.br/wp-content/uploads//2020/04/WINDOWS-LINUX-990x556.png" width="250px">

 - Linux, Ubuntu, Centos etc

### Disk - Information, space free and use
```
lsblk
```
or
```
sudo df -Th
```

### Restart, reboot
```
sudo reboot
```

### How can I copy the contents of a folder to another folder in a different directory using terminal?
The advantages of rsync are:
After the initial sync, it will then copy only the files that have changed.
You can use it over a network, convenient for files in $HOME, especially config files.
```
rsync -a source/ destination/
```

### How I can know the IP address of other users logged at the same remote machine?
```
w
```

### How to find a file from any directory
```
find / -iname nameFile*
```

### What is the difference between kill and Pkill command?
show only process with name ssh of root
```
pgrep -u root ssh
```

### To delete a single file, use the rm or unlink command followed by the file name:
```
unlink filename
rm filename
```

https://www.showmetech.com.br/wp-content/uploads//2020/04/WINDOWS-LINUX-990x556.png

### How to compress a whole directory (including subdirectories) using TAR in Unix based OS with the CLI
```
tar -zcvf result-filename.tar.gz path-of-directory-to-compress
```
Reference https://ourcodeworld.com/articles/read/642/how-to-compress-a-whole-directory-including-subdirectories-using-tar-in-unix-based-os-with-the-cli

### Command Line Moving
```
mv /home/jack/testfile /home/jack/testfile2
```
or, if you’re already within /home/jack:
```
mv testfile testfile2
```

### Copy between Windows/Linux Using PSCP - Putty SCP (Secure Copy) to transfer files securely
From Linux to Windows, used porta 22022 no Linux
```
pscp -P 22022 root@162.241.103.39:/root/app/bkp/postgresbackup.tar ../Documents/Hostgator/bkp-server/
```

* Copy from Windows to Linux
```
pscp -P 22022 robots.txt root@162.241.103.39:/root/app/bkp/
```
Reference https://www.youtube.com/watch?v=Sc0f-sxDJy0

### Crontab in Linux with 20 Useful Examples to Schedule Jobs
* How to List Crontab
To view crontab entries of current users use the following command.

```
crontab -l
```
Use -u followed by the username to view crontab entries of the specified user.
```
crontab -u username -l
```
ref https://tecadmin.net/crontab-in-linux-with-20-examples-of-cron-schedule/

##Linux C E N T O S commands

### To remove non-empty directories and all the files within them, use the ```rm``` command with the ```-r``` (recursive) option:
```
rm -rf dirname
```
Reference: https://linuxize.com/post/how-to-remove-files-and-directories-using-linux-command-line/

### To initiate a connection, type: 
```
ssh username@xxx.xxx.xxx.xxx. ...
```

### Free distribution for SSL certificates
```
https://certbot.eff.org/
``` 
References: https://app.rocketseat.com.br/node/nivel-06/group/deploy-da-aplicacao/lesson/configurando-dominio-e-ssl

### Track DNS propagation
```
https://www.whatsmydns.net/
```

### Linux Command To List Current Logged In Users
```w``` command – Shows information about the users currently on the machine, and their processes. <p>
```who``` command – Display information about users who are currently logged in.<p>
```users``` command – See the login names of the users currently on the system, in sorted order, space separated, on a single line. It reads all information from /var/run/utmp file.


### The pwd command displays the full, absolute path of the current, or working, directory. It’s not something you’ll use all the time, but it can be incredibly handy when you get a bit discombobulated.
 ``` 
 pwd
 ```
 ### How to get full path of a file?
 ```
 readlink -f file.txt
 ```
 ###Directory Commands###
 ``` 
To navigate into the root directory, use "cd /"

To navigate to your home directory, use "cd" or "cd ~"

To navigate up one directory level, use "cd .."

To navigate to the previous directory (or back), use "cd -"

To navigate through multiple levels of directory at once, specify the full directory path that you want to go to. For example, use, "cd /var/www" to go directly to the /www subdirectory of /var/. As another example, "cd ~/Desktop" will move you to the Desktop subdirectory inside your home directory.
 ```

**L I N U X - Centos Update docker**
 ``` 
 yum update docker
 yum install docker-ce docker-ce-cli containerd.io
 ```
 
 **L I N U X - Version Docker**
 ``` 
systemctl status docker
 ```
 
 **L I N U X - Restart service docker**
 ``` 
 systemctl restart docker
 ``` 


- Outdated network config utility.
```
ifconfig
```

- List Network Interfaces
```
ip link show
Or
netstat -i
```

List ports in use
```sudo netstat -tulpn```

list details programm (pid id do program run)
```ps pid```


Where to find SSH Login log files
Monitoring in real time
```tail -f -n 50 /var/log/secure | grep sshd```


### Install pm2
```
sudo install -g pm2
```

List managed applications
```pm2 list```

Terminal Based Dashboard
```pm2 monit```


Firewall Centos (Allow ports (from to)
iptables -I INPUT -p tcp --dport 30000:65534 -j ACCEPT


# U B U N T U - ![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbgLL5KvscvtZOc1zXBSQT6YQMAQLogzZvpw&usqp=CAU)

- Uptade list packages
```
apt-get update
```

- Install app, example curl
```
apt-get install curL --yes
```

## Install D O C K E R
```
curl -fsSL https://get.docker.com | bash
```

* List files and folder
```
ls -la
```

### Run service pm2
 ```
pm2 start dist/shared/infra/http/server.js --name power-back
 ```
 
* Alwasy restart pm2
 ```
pm2 startup systemd
 ```
 
### [PM2] Freeze a process list on reboot via:
```
pm2 save
```

* Other commands pm2
 ```
pm2 logs
pm2 monit
 ```
 
* Restart service pm2
 ```
pm2 restart power-back
 ```

* Stopped service pm2
 ```
pm2 stop power-back
 ```
 
### Run process in Linux with PM2 to NextJs site-arch

Used npm
https://medium.com/@indiesk/deploying-a-nextjs-app-in-production-with-custom-server-using-nginx-and-pm2-786ccf9444c5
```
pm2 start --name "nameService" npm -- run start
```
Used Yarn
https://dev.to/reactstockholm/setup-a-next-js-project-with-pm2-nginx-and-yarn-on-ubuntu-18-04-22c9

```
pm2 start yarn --name "nameService" --interpreter bash -- start
pm2 show nameService
```
 
 ### Settings to multi domains with app NextJs
 1. Realize o backup do arquivo de configuração do Apache:
cp -vp /etc/apache2/conf/httpd.conf{,-BKP}

2. Feito o backup, descomente as linhas de include no vhosts do domínio em questão, devendo ser feito tanto para HTTP quanto HTTPS:
vim /etc/apache2/conf/httpd.conf

3. Após acessar o arquivo, procure as linhas a seguir e remova o #:
Include "/etc/apache2/conf.d/userdata/std/2_4/USUARIO/DOMINIO.COM/*.conf"
Include "/etc/apache2/conf.d/userdata/ssl/2_4/USUARIO/DOMINIO.COM/*.conf"

4. Agora crie os diretórios:
mkdir -p /etc/apache2/conf.d/userdata/std/2_4/USUARIO/DOMINIO.COM
mkdir -p /etc/apache2/conf.d/userdata/ssl/2_4/USUARIO/DOMINIO.COM

5. Crie os arquivos a seguir, atente-se para a diferença no path com std e ssl:
vim /etc/apache2/conf.d/userdata/std/2_4/USUARIO/DOMINIO.COM/USUARIO.conf

6. Adicione o seguinte conteúdo ao arquivo de configuração no path std:
RewriteEngine on
RewriteCond %{HTTPS} off
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
ProxyPass "/path" "http://destino.com/"

7. Supondo que o domínio exemplo.com está hospedado conosco, e o webmail.exemplo.com é utilizado em outro local e o cliente deseja que o acesso exemplo.com/webmail seja redirecionado para o outro local. Configure da seguinte forma:
RewriteEngine on
RewriteCond %{HTTPS} off
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
ProxyPass "/webmail" "http://webmail.exemplo.com/"

8. Feito isso, iremos configurar agora o arquivo no path ssl:
ProxyPass "/path" "http://destino.com"

9. E utilizaremos o mesmo exemplo do path std:
ProxyPass "/webmail" "http://webmail.exemplo.com/"

10. Ao finalizar a configuração em ambos os arquivos, basta executar os comandos a seguir:
service httpd restart

### Apache redirect to another port
```config
# Change 200.201.10.80 by yourIP
<VirtualHost 200.201.10.80:80>
ProxyPreserveHost On
ProxyRequests Off
ServerName myhost.com
ServerAlias ww.myhost.com
ProxyPass / http://localhost:8080/
ProxyPassReverse / http://localhost:8080/
</VirtualHost>
```
reference: https://stackoverflow.com/questions/8541182/apache-redirect-to-another-port
