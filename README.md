# L I N U X - ![](https://www.showmetech.com.br/wp-content/uploads//2020/04/WINDOWS-LINUX-990x556.png)

 - Linux, Ubuntu, Centos etc

# linux-C E N T O S - ![](https://miro.medium.com/proxy/0*gtVzHfWNRqKLbB4p.png)

Linux C E N T O S commands

### Linux Command To List Current Logged In Users
```w``` command – Shows information about the users currently on the machine, and their processes. <p>
```who``` command – Display information about users who are currently logged in.<p>
```users``` command – See the login names of the users currently on the system, in sorted order, space separated, on a single line. It reads all information from /var/run/utmp file.

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
- sudo netstat -tulpn

list details programm (pid id do program run)
- ps pid


Where to find SSH Login log files
Monitoring in real time
tail -f -n 50 /var/log/secure | grep sshd


List managed applications
pm2 list

Terminal Based Dashboard
pm2 monit


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

* Use Vim
```
vim name_file
```

* Edition Vim, only use keyboard <strong>'i'</strong>, after use, keyboard <strong>ESC</strong> and <strong>:wq</strong> and <strong>ENTER</strong>
```
i
ESC
:wq
ENTER
```

Run service pm2
 ```
pm2 start dist/shared/infra/http/server.js --name power-back
 ```
 
* Alwasy restart pm2
 ```
pm2 startup systemd
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
