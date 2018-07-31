#### jenkins安装

> 如果服务器没有安装docker和docker-compose的请移步到我另一个脚本，运行脚本就能把这两个都装好(自动配置了国内镜像地址) 

- 环境装好以后 进入 项目文件夹`env-build`下，有个脚本 运行安装

- 然后后台运行jenkins
    
     启动之前先执行下面的命令
     
     mkdir /home/docker
     
     chmod 777 /home/docker(这里主要是为了防止docker和宿主机权限不足，因为容器的用户为1000 而宿主机是 root)
  
      docker-compose up -d

      运行完成后打开浏览器访问：`${ip}:${port}` 端口默认8080 我改成了 8888 因为我的8080被占用了

      访问成功后，会让输入 Administrator password  
      
      cd /home/docker/jenkins/secrets
      
      cat cat initialAdminPassword
      
      这样就能看到密码啦
      

- 输入刚才拿到的密码, 登录到jenkins  左边第一个框就好 就会自动给我们安装一些插件 等他安装完

![安装插件](https://github.com/niezhiliang/jenkins-docker-maven-git/blob/master/env-build/imgs/plugin.jpeg)

- 下载完成后就要开始添加账号密码啦 账号密码记住就好 下次还要登录用

![演示gif](https://github.com/niezhiliang/jenkins-docker-maven-git/blob/master/env-build/imgs/welcome.jpg)

####   配置Jenkins   Publish Over SSH  配置SSH登陆centos

- 在Jenkins所在的服务器  使用下面命令 生成一个秘钥对

    ssh-keygen -t rsa 
    
    这里输入命令后一直回车就好，生成了就会出现下面这个界面  会有两个文件生成在 /root/.ssh文件夹下面 
    id_rsa(私钥) 和 id_rsa.pub（公钥）
    

![演示gif](https://github.com/niezhiliang/jenkins-docker-maven-git/blob/master/env-build/imgs/ssh.jpg)


- 此时登录到项目要发布的服务器上执行如下指令
    
        cd ~

        mkdir .ssh

        cd .ssh

        touch authorized_keys

        将Jenkins生成的公钥内容复制到这个文件里面

        然后重新启动项目服务器的ssh连接

        service sshd restart
    
- 回到Jenkins登录的页面 
    
    系统管理 =>   管理插件 => 可选插件 =>右上角搜索框输入 Publish => 找到Publish Over SSH 并安装 => 系统管理 =>
     系统设置 => 移到页面底部 => Publish over SSH 配置一下
     
     
![演示gif](https://github.com/niezhiliang/jenkins-docker-maven-git/blob/master/env-build/imgs/config.jpg)    






    
    
    
