---
title: "如何防止Google Colab 自動斷線"
date: 2020-07-31T16:23:22-00:00
categories:
  - Machine Learning
tags:
  - colab
  - machine learning
  - javascript
  - python
header:
  image: /assets/images/colablogo.jpg
---
## 什麼是Colab?  
Colab是Google所提供的一項很棒的資源  
你可以在上面跑你的Pyhon程式  
當作Google免費幫你host的Jupyter Notebook  
除此之外，Colab還有提供免費的GPU甚至是TPU的運算資源讓你任意揮霍  
強烈建議對AI, 機器學習或是data science領域有興趣的人都能夠試試看  
  
---
## Colab的問題  
雖然Colab很好用，但是也有一些不方便的地方  
像是每30分鐘假如沒有動作的話，Colab會自動將你斷線，釋放資源給其他的使用者，在這個時候你的資料就都會不見了

---

## 解決方法  

在你的瀏覽器Console中加入以下的指令  
Ctrl+ Shift + i 打開console，然後輸入  
```javascript
function ClickConnect(){
console.log("Working"); 
document.querySelector("colab-toolbar-button").click() 
}setInterval(ClickConnect,60000)
```  

假如有任何問題歡迎留言或是來信向我詢問  

[參考來源](https://medium.com/@shivamrawat_756/how-to-prevent-google-colab-from-disconnecting-717b88a128c0)