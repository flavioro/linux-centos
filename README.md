# L I N U X - ![](https://www.showmetech.com.br/wp-content/uploads//2020/04/WINDOWS-LINUX-990x556.png)

 - Linux, Ubuntu, Centos etc

# linux-C E N T O S - ![](https://miro.medium.com/proxy/0*gtVzHfWNRqKLbB4p.png)

Linux C E N T O S commands

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
*apt-get update*

- Install app, example curl
*apt-get install curL --yes*
