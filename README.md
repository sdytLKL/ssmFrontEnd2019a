# ssmFrontEnd2019a
 可以这样实现SSM的前后端分离开发。

SSM前后端分离开发

本项目仅用于SSM项目的前端开发（相当于前后端分离后的前端部分）。

一、开发环境：

Windows7旗舰版；

Eclipse4.5（Mars.2）（with JDK8）；

apache-maven-3.6.0；

apache-tomcat-7.0.77。

二、原理：

分离前是这样的：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/1.jpg)

分离后是这样的：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/2.jpg)
 
可见，已经没有了dao、service、mybatis、mapper等持久层。取而代之的是web里临时加入了虚拟后端vtctrl（对控制器和服务层略作修改形成）。持久数据可以不再使用数据库，而是存储在其它文件里（本例是采用resources里的xml文档Seckill.xml和SuccessKilled.xml保存数据）。
换句话说相当于在SSM框架里，用一个虚拟的服务层临时代替了原来的服务层。从而实现了SSM前后端的完全分离开发。如下图：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/3.jpg)
 
虚拟后端的设计原则是，其一，对于前端开发者应该是透明的，即不应该感觉到虚拟后端的存在；另外，项目文档结构尽可能保持原状，以利于未来前后端之间的衔接（接驳）容易地进行。

三、若干要点：

开发者需要将项目seckill2导入自己的Eclipse工作空间中。该工作空间最好单独安装Maven环境。像这样：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/4.jpg)
 
![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/5.jpg)

首次导入最好对该项目进行Maven更新，确保依赖正确。即这样：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/6.jpg)

项目运行前，请别忘了修改项目的Web上下文根为“/”。

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/7.jpg)
 
将项目部署到Tomcat7服务器并启动后，用地址：http://localhost:8080/访问：

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/8.jpg)
 
接下来就可以进行各项前端开发了。

![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/9.jpg)


![](https://github.com/sdytLKL/ssmFrontEnd2019/blob/master/images/10.jpg)

 

 