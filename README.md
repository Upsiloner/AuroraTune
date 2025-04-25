# AuroraTune

## ⚙️ 项目启动与资源配置

### 1. 镜像配置
为了加速 Docker 镜像的拉取速度，您可以使用国内的镜像源。例如，您可以使用阿里云、DaoCloud、网易等提供的镜像服务。

在 Linux 系统上，执行以下命令：
```bash
sudo mkdir -p /etc/docker
sudo vim /etc/docker/daemon.json
```
将以下内容添加到 daemon.json 中：
```bash
{
  "registry-mirrors": [
    "https://mirror.baidubce.com",
    "https://docker.mirrors.ustc.edu.cn",
    "https://hub-mirror.c.163.com"
  ]
}
```
在 Windows 系统上，您可以通过 Docker Desktop UI 配置加速器，选择 Settings > Docker Engine，然后在配置中添加镜像源。

最后重启 Docker 服务以使配置生效：
```bash
sudo systemctl restart docker
```

### 2. 启动所有服务
在项目根目录下，使用以下命令启动 Docker 容器：
```bash
docker compose up --build
```

### 3. 失败时如何单独拉取镜像

如果在构建过程中遇到失败，或者你希望重新拉取镜像，可以单独拉取镜像来更新或修复镜像：
```bash
docker pull your-image
```
在某些情况下，可能会需要删除本地缓存的镜像后重新拉取：
```bash
docker rmi <image_id>  # 删除本地镜像
docker-compose up --build  # 重新构建和启动服务
```

## 🐋 docker-compose 配置

### 1. 邮箱 SMTP 代理

替换如下字段：
```bash
services:
    backend:
        environment:
            - EMAIL_SENDER=your_email
            - EMAIL_PASSWORD=your_authorization_code
            - EMAIL_SENDER_NAME=your_name
            - SMTP_SERVER=smtp.xxx.com
            - SMTP_PORT=465
```