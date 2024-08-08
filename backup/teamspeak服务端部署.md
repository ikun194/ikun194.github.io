teamspeak是一款语音聊天软件，他支持把服务端部署到自己的服务器上，接下来将介绍如何部署。  

## 准备工作  
* linux系统，我这里是Ubuntu22.04
* docker环境，没有的话可以使用`curl -fsSL https://get.docker.com -o get-docker.sh sh get-docker.sh`来安装。  
## 安装并配置  
使用ssh链接到服务器，使用这个命令来安装teamspeak的docker容器:  
~~~
docker run -p 9987:9987/udp -p 10011:10011 -p 10022:10022 -p 10080:10080
~~~  
安装成功后放行服务器防火墙（或者安全组）的TCP 41144，10022，10080，30033，10011，10443，9000，和UDP 9987端口。   

然后输入`docker ps -a`，找到teamspeak前面的字符为容器id，使用`docker logs -f [容器id]`查看日志，在下面I M P O R T A N T下面找到token，把他复制下来，  
![image](https://img.bear556.xyz/i/2024/08/08/j3qjl2.png)
打开你的teamspeak客户端（我这里用ts5来演示）输入你的服务器ip，连接成功后会出现输入权限密钥，把你刚刚复制的token粘贴进去，就可以获取服务器的管理权限了。  

![image](https://img.bear556.xyz/i/2024/08/08/j4j9k8.png)

需要注意的是，服务器日志里的权限密钥是一次性的，在你成功登录客户端之后就会失效，你可以重新生成一个密钥来做备份，请到服务器的管理页面-权限密钥-点击serveradmin组-生成密钥  
![image](https://img.bear556.xyz/i/2024/08/08/j54ayg.png)  

复制下来并妥善保管，任何拥有此密钥的人都会获得你服务器你管理权限。  
 
## 完成  
现在你就可以香你的朋友分享你的teamspeak服务器的地址并语音开黑了