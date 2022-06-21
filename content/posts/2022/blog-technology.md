---
title: "部落格技術棧"
date: 2022-06-21T19:57:36+08:00
tags: ["blog"]
categories: ["輕技術"]
---

#### 這個部落格使用了哪些技術呢
- Hugo
- Cloudflare Pages
- Cloudflare Registrar

##### Hugo
一開始原先是想和朋友一起搭建一個類似 [中國掘金](https://juejin.cn/) 的網站，讓大家可以一起分享技術文章，但後來因大家都比較忙就改為製作個人的技術部落格，因此在搭建上就選擇比較快速簡單的方法。

一開始考慮過使用 [Eleventy](https://www.11ty.dev/)，但實際使用後覺得文檔比較缺乏也不想使用 Node.js 環境，因此才改為使用 [Hugo](https://gohugo.io/)，目前使用下來還挺滿意的，主題是使用 [LoveIt](https://hugoloveit.com/)，幾乎沒什麼更改就直接用了。

優點: 
- 資料夾結構較單純
- 編譯快速
- 可即時預覽
- 文檔及生態豐富

##### Cloudflare Pages
這個部落格目前是託管在 [Cloudflare Pages](https://pages.cloudflare.com/)，比較多人可能會選擇 [GitHub Pages](https://pages.github.com/) 或是 [NetLify](https://www.netlify.com/)，GitHub Pages 是覺得設定比較麻煩而 NetLify 雖然有自動構建但速度方面好像比較慢，最後是看到 Cloudflare Pages 新推出才想來嘗鮮看看。

優點:
- 免費
- 可與 GitHub 連結自動構建
- 免費 SSL 配置
- Cloudflare 全球 CDN 支持

##### Cloudflare Registrar
[Cloudflare Registrar](https://www.cloudflare.com/zh-tw/products/registrar/) 也是新推出的購買網域地方，因為想說託管已經使用 Cloudflare 了就乾脆連網域也一起在這邊買設定管理也方便。價格方面是有比 [Google Domains](https://domains.google.com/registrar) 便宜一點，也不會像 [GoDaddy](https://tw.godaddy.com/) 價格在第二年暴增。