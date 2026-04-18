# one-api docker指南

## 配置国内镜像

### 安装

https://zhuanlan.zhihu.com/p/24499741863

### 镜像

https://zhuanlan.zhihu.com/p/710507502

编辑/etc/docker/daemon.json文件，在里面添加下面的内容：

```json
{ 
  "registry-mirrors" : 
    [ 
      "https://docker.m.daocloud.io",
      "https://docker.xuanyuan.me", 
      "https://docker.1ms.run"
    ] 
}
```

## docker启动One-API

https://cloud.tencent.com/developer/article/2504010

```bash
docker run --name one-api -d --restart always -p 3000:3000 -e TZ=Asia/Shanghai -v /dockerData/one-api:/data justsong/one-api
```

### ollama启动/修改
- 先更改配置
```bash
sudo vim ollama.service
```

- 保存后
```bash
sudo systemctl daemon-reoload
sudo systemctl disable ollama
sudo systemctl enable ollama
sudo lsof -i :11434 # 或者sudo ps aux | grep ollama
kill -9 [pid]
# 自动重启
```
