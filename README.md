# 说明

> app部署代码, config配置文件，data附属数据的持久化存储，shared共享区


1. 更新系统
2. 安装Docker
3. 创建部署用户, 并赋予Docker 权限

    sudo usermod -aG docker deployer

4. 初始化部署目录

    cd ~/apps/
    git clone https://github.com/agideo/docker-deployment.git <app_name>

5. cp docker-compose.yml.example docker-compose.yml
6. 添加public key 到 config/ssh_authorized_keys
7. docker-compose up -d
8. check ssh-agent

   de chown root: ~/.ssh/authorized_keys
   de chmod 600 ~/.ssh/authorized_keys

9. check cap

   de cap production deploy:check
   de cap production deploy

10. check rails
11. docker nginx config
12. server nginx config
13. setting cdn
14. ssl 证书

```
curl https://get.acme.sh | sh
acme.sh --issue -d wzhw-wxsc2.s168.do8.cc -w /home/deployer/apps/wzhw_wxsc2_deploy/app/shared/public

acme.sh --installcert -d wzhw-wxsc2.s168.do8.cc \
               --keypath       /home/deployer/apps/wzhw_wxsc2_deploy/ssl/wzhw-wxsc2.s168.do8.cc.key  \
               --fullchainpath /home/deployer/apps/wzhw_wxsc2_deploy/ssl/wzhw-wxsc2.s168.do8.cc.pem \
               --reloadcmd     "sudo service nginx reload"

```
15. 测试证书会自动更新
16. 设置sentry
17. 设置sentry 会自动gengx
18. 设置数据库备份
19. 设置数据库备份检查




