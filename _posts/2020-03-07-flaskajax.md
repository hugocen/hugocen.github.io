---
title: "Flask跟Ajax的互動方法"
date: 2020-03-07T22:38:22-00:00
categories:
  - Web
tags:
  - web
  - python
  - flask
  - jquery
  - ajax
---
  
直接給範例  
Web端
```javascript
$.ajax({
    url: url,
    type:"post",
    data: {'state': state},
    dataType: 'json',
    success:function(data){
        console.log(data)
    },
    error:function(e){
    }
})
```  
Server 端  
```python
@app.route('/coronavirus_yahoo', methods=['POST'])
def coronavirus_yahoo():
    state = request.form['state'].lower()
    return '
```