---
title: "如何在Docker Container內建立SSH Server"
date: 2019-09-24T15:34:30-04:00
categories:
  - Docker
tags:
  - docker
  - ssh
  - linux
header:
  image: /assets/images/docker.png
  overlay_filter: 0.5
---
<!-- # 如何用 ssh 連線到 Docker Container -->
## 起源
Docker是一個方便的工具
能讓你建立輕量的虛擬環境  
不但不用擔心會汙染你的工作環境  
運作效能也非常強大  
那麼很自然地會想要將所建立的docker container當作server來使用  
可是每次要進入container環境時要先連線docker host的機器然後在attach container  
這樣的做法太過麻煩  
因此我嘗試在container內部建立ssh server  
未來就能直接使用ssh連線到container  
## 方法  
首先在Dockerfile中寫好ssh的安裝指令  
並且將entrypoint設定好  
entrypoint的用意為 每當container開始運行時重啟ssh服務  
dockerfile範例:
```dockerfile
FROM ubuntu:18.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        curl \
        wget \
        git \
        gcc \
        ssh \
        vim && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT service ssh restart && bash
```

當docker run建立container時 記得開啟對外的port  
參數為 -p 外部port:內部port  
```bash
docker run -p 1234:22 helloworld:latest
```
運行container之後 要先更改密碼  
```bash
passwd
```
再來要更改ssh的設定  
ssh的設定檔在Ubuntu系統的預設位置為:  
```bash
/etc/ssh/sshd_config
```
把PasswordAuthentication以及PermitRootLogin的註解拿掉 並更改設定為yes
``` xml
...
PermitRootLogin yes
...
PasswordAuthentication yes
...
```
最後重啟ssh服務就好囉
```bash
service ssh restart
```  

假如有任何問題歡迎留言或是來信向我詢問  