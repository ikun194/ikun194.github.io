我建的站：[赛博扫盲手册](https://pcbook.top)

# 安装docsify  
~~~
npm i docsify-cli -g
 # 安装docsify
docsify init ./docs
 # 初始化并创建./docs文件夹
~~~  
安装成功了，可以看到对应目录下出现了这些文件：  
-   `index.html` 入口文件
-   `README.md` 会做为主页内容渲染
-   `.nojekyll` 用于阻止 GitHub Pages 忽略掉下划线开头的文件  

现在就可以编辑`README.md`来修改主页内容了，你也可以使用`docsify serve ./docs`来在本机3000端口上启动一个实时更新的开发服务器来查看你的更改。   
# 多页文档  
直接在docs目录下新建md文件，通过`域名/文件名`进行访问。  
## 定制侧边栏  
在创建多页文档之后你会发现，只能手动输入地址去访问对应的文档，这时候就需要通过编辑侧边栏来实现，在`index.html`里找到`window.$docsify = {`在下面添加`loadSidebar: true`    
~~~html
<!-- index.html -->

 <script>
    window.$docsify = { 
        loadSidebar: true 
     } 
 </script>
 ~~~
 然后创建`sidebar.md`文件，在里面用markdown链接格式填入你的页面的地址。。  
 ~~~
 * 基础篇
 * [前言](/)
 * [硬件](1)
 * [操作系统](2)
 * [浏览器](3)

~~~
你问为什么我后面填的是123？因为我的文件名就是1.md，2.md，3.md。。。。  
# 更多配置修改  
[官方文档](https://docsify.js.org/#/zh-cn/configuration)  
都是在`index.html`里的`window.$docsify = {`添加的，插件也是