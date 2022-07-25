#创建运行用户与相关目录
useradd -u 200 -g 200 -s /sbin/nologin nexus
mkdir -p /opt/nexus3
chown -R nexus:nexus /opt/nexus3

#启动服务
docker-compose up -d
