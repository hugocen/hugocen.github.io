---
title: "如何在three.js中顯示中文3D模組"
date: 2020-03-22T22:38:22-00:00
categories:
  - Web
tags:
  - web
  - javascript
  - threejs
---
  
在three.js 給的3D文字範例當中  
假如直接顯示中文字會變成一堆的????  
會造成這樣的原因是因為範例中所使用的字體並不支援中文  
因此我們得自己找到中文字體並且用three.js 載入  
  
---
## 字體檔  
字體的部份可以使用網路上開源的免費中文字體(日文, 韓文,...等等也通用)  
然而在three.js 當中  
沒辦法直接讀取一般字體的.ttf 檔  
然需要轉成typeface.js 的格式  
[Facetype.js](https://gero3.github.io/facetype.js/) 這個網站能夠輕鬆的將ttf檔案轉換成typeface.js 的格式  

---

## three.js 讀取字體  

在three.js 當中讀取字體的方式如下方的code 所示  
將'samplefont.typeface.json' 當中的路徑改為[Facetype.js](https://gero3.github.io/facetype.js/) 中所轉換出來.js 檔即可

```javascript
var font = undefined
var loader = new THREE.FontLoader();
loader.load( 'samplefont.typeface.json', function ( response ) {
    font = response;
} );
```  