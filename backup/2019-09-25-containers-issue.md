---
title: "Docker Containers 不能互相連線"
date: 2019-09-25T18:12:00-00:00
categories:
  - Docker
tags:
  - docker
  - port
  - linux
---

為了隔離環境  
常常在Docker 中建立了很多的container  
有時後會發現 就算有開通container的對外port  
container 之間仍然無法通訊  
這裡提供一個可能的解決辦法  
在Docker 的host 中輸入
```bash
sudo firewall-cmd --permanent --zone=public --add-rich-rule='rule family=ipv4 source address=172.17.0.0/16 accept' 
sudo firewall-cmd --reload
```