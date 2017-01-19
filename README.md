# 说明

> app部署代码, config配置文件，data附属数据的持久化存储，shared共享区


1. 更新系统
2. 安装Docker
3. 创建部署用户, 并赋予Docker 权限

    sudo usermod -aG docker deployer

4. 初始化部署目录
  
    cd ~/apps/
    git clone https://github.com/agideo/docker-deployment.git <app_name>
