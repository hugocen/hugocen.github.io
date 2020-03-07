---
title: "如何更改flask預設的template以及templates資料夾"
date: 2020-03-07T22:38:22-00:00
categories:
  - Web
tags:
  - web
  - python
  - flask
---
  
使用flask的Blueprint模組  
當然Blueprint有其他的功能以及用途  
只是我現在還沒摸透  
```python 
admin = Blueprint('admin', __name__, template_folder='templates',templates_folder='static/')
```  
