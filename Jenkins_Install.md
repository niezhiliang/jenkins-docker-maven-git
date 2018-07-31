#### jenkins安装

> 如果服务器没有安装docker和docker-compose的请移步到我另一个脚本，运行脚本就能把这两个都装好(自动配置了国内镜像地址) 

- 环境装好以后 进入 项目文件夹`env-build`下，有个脚本 运行安装

- 然后后台运行jenkins
  
      docker-compose up -d

      运行完成后打开浏览器访问：`${ip}:${port}` 端口默认8080 我改成了 8888 因为我的8080被占用了

      访问成功后，会让输入 Administrator password  我们进入docker 容器内部查看一下
      
      docker exec -it jenkins /bin/bash
      
      cd /var/jenkins_home/secrets/
      
      cat cat initialAdminPassword
      
      这样就能看到密码啦
      

- 输入刚才拿到的密码, 登录到jenkins  左边第一个框就好 就会自动给我们安装一些插件 等他安装完

![安装插件](https://github.com/niezhiliang/springbootwebsocket/blob/master/demo.gif)

- 下载完成后就要开始添加账号密码啦 账号密码记住就好 下次还要登录用

![演示gif](https://github.com/niezhiliang/springbootwebsocket/blob/master/demo.gif)




    
    
    
