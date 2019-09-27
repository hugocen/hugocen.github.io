---
title: "如何在CentOS 7 中安裝 Python 3.6"
date: 2019-09-27T18:10:00-00:00
categories:
  - Linux
tags:
  - linux
  - python
  - yum
  - centos
---

在Centos 7下 預設的Python 3 安裝版本為3.5  
要安裝3.6版本可參考以下指令

```bash
sudo yum install -y https://centos7.iuscommunity.org/ius-release.rpm
sudo yum update
sudo yum install -y python36u python36u-libs python36u-devel python36u-pip
python3.6 -V
pip3.6 -V
```