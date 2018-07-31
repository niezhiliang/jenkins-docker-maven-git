# jenkins-docker-maven-git
jenkins-docker-maven-git 自动化部署

#### jenkins安装

> 如果服务器没有安装docker和docker-compose的请移步到我另一个脚本，运行脚本就能把这两个都装好(自动配置了国内镜像地址) 

- 环境装好以后 进入 项目文件夹`env-build`下，有个脚本 运行安装

- 然后后台运行jenkins
  
    docker-compose up -d
    
    运行完成后打开浏览器访问：`${ip}:${port}` 端口默认8080 我改成了 8888 因为我的8080被占用了
    
    访问成功后，会让输入 Administrator password 
    
    
    
    
