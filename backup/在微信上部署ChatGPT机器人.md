## 简介
ChatGPT近期以强大的对话和信息整合能力风靡全网，可以写代码、改论文、讲故事，几乎无所不能，这让人不禁有个大胆的想法，能否用他的对话模型把我们的微信打造成一个智能机器人，可以在与好友对话中给出意想不到的回应，而且再也不用担心女朋友影响我们~~打游戏~~工作了。   
***
## 准备材料  
* 一个能访问OpenAI访问的服务器
* OpenAI apikey  
* docker环境  
* 健全的脑子  

## 下载docker-compose.yml  
在终端中输入以下命令
~~~
wget https://open-1317903499.cos.ap-guangzhou.myqcloud.com/docker-compose.yml
~~~ 
然后修改`docker-compose.yml`  

~~~
vim docker-compose.yml
~~~


按a进入编辑模式，使用方向键移动光标，找到`OPEN_AI_API_KEY`并改为你自己的OpenAI apikey，找到`GROUP_NAME_WHITE_LIST`，改为你想使用机器人的群聊名称  

## 启动容器
在 `docker-compose.yml` 所在目录下执行以下命令启动容器：
~~~
sudo docker compose up -d
~~~
运行 sudo docker ps 能查看到 NAMES 为 chatgpt-on-wechat 的容器即表示运行成功

## 登录微信
输入以下命令来查看日志  
~~~
sudo docker logs -f chatgpt-on-wechat
~~~
用微信扫描终端输出的二维码登录即可