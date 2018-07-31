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




    
    
    
