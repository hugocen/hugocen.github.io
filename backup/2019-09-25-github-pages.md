---
title: "如何用 Github Pages 建立免費的個人Blog"
date: 2019-09-25T16:07:00-00:00
categories:
  - Frontend
tags:
  - Frontend
  - git
  - github
  - pages
header:
  image: /assets/images/githubpages.png
  overlay_filter: 0.5
---
<!-- # 如何用 Github Pages 建立免費的個人Blog -->

## Github pages
### [Github pages](https://pages.github.com/)
Github 除了提供Git Server的功能之外  
也提供了免費的靜態網站伺服器  


## 建立 Github Pages
建立Github Pages的方法很簡單  
在Github新建一個repository 名字為  
> 使用者名稱.github.io  

接著在 https://使用者名稱.github.io    
就能看到你放上去的網站

這裡要特別注意  
使用者名稱填入任何非該repository擁有者的帳號都會失敗  
不過也可以藉由更改repository名稱的方式做修正

當repositor建好之後 把網頁丟上去就結束啦(誤)


## 使用 Jekyll 產生靜態網頁
### [Jekyll](https://jekyllrb.com/)
Github Pages 原生支援 Jekyll  
Jekyll 可以使用 Markdown 語法來撰寫網頁 也有很大的客製化空間  
Jekyll 也提供了很多不同的主題以及套件可以安裝  
這裡就不一一介紹了  
直接拉樣板來用!


## 套用 Minimal Mistakes 的 Jekyll 主題
[Minimal Mistakes Jekyll theme](https://mmistakes.github.io/minimal-mistakes/)  
Minimal Mistakes是專門為了個人網站以及部落格用途的 Jekyll 主題  
用法很簡單  
直接fork [remote theme starter](https://github.com/mmistakes/mm-github-pages-starter) 這個repository  
然後把repository的名稱改成自己的  
> 使用者名稱.github.io  


裡面有內建好不同的文章範例可以參考  
或是可以參考[Minimal Mistakes 的官方文件](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) 來做修改  
如此一來就有一個美觀又免費的Blog啦