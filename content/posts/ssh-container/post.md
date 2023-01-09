---
title: "How to assess docker containers via SSH" 
date: 2023-01-10T00:31:03+08:00
# weight: 1
# aliases: ["/first"]
tags: ["docker", "ssh"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: true
draft: false
hidemeta: false
comments: false
description: "How to assess docker containers via SSH"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/hugocen/hugocen.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
## Overview

This article will show you how to assess docker containers via SSH.

## Prerequisites

- Docker

## Steps

1. Create a docker container with SSH service by using the following Dockerfile:

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

2. Build the docker image:

```bash
docker build -t ssh-container .
```

3. Run the docker container:

```bash
docker run -p 2222:22 --name ssh-container ssh-container
```

`-p 2222:22` means that the port 2222 of the host is mapped to the port 22 of the container.

4. Change the password of the root user:

```bash
passwd
```

5. Edit the `/etc/ssh/sshd_config` file:

```bash
vim /etc/ssh/sshd_config
```

Uncomment the following line and change the value to `yes`:

```xml
...
PermitRootLogin yes
...
PasswordAuthentication yes
...

```

6. Restart the SSH service:

```bash
service ssh restart
```

7. SSH to the container:

```bash
ssh root@localhost -p 2222
```

## Conclusion

In this article, we have learned how to assess docker containers via SSH.
