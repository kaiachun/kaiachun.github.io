---
layout: blog
title: '用GitHub Pages建立技術部落格'
date: 2021-02-05 18:20:34
categories: learn
tags: study
image: 'https://blinkbits.com/wp-content/uploads/2018/10/Blogs-1.jpg'
lead_text: '將自己的學習檔案用Git以Blog方式在網頁上公開'
---
## Github Pages 介紹
* 優點:  
1. 免費，有Github 帳號就可建立  
2. 支援 Jekyll ，可以快速建立  

* 缺點:  
1. 只能呈現靜態頁面，無法讀取資料庫、進行使用者登入等  
2. 所有 Github Pages 皆是公開的

## 使用素材
1. Github 帳號  
2. Git bash  
3. Jekyll  
4. Disqus(加選)  
5. Github Desktop(加選)  

## 實作流程
### 建立Github Pages 倉庫
1. 建立 Github Pages 用的 Repository  
![](https://i.imgur.com/3EIcPGX.png)
2. 上傳blog或測試網頁
(可自己寫或使用現成版型，可以參考:  
http://jekyllthemes.org/  
https://jekyllthemes.io/  
https://jekyllthemes.io/free  
)
3.	在 setting 點選網址即可執行
![](https://i.imgur.com/kSPhAtT.png)


### 在本地端測試
1.  安裝 Jekyll 環境  
目的為方便測試用  
(詳細安裝步驟可參考https://wcc723.github.io/jekyll/2014/01/13/windows-jekyll-server/)  

2. 開啟 Start Command Prompt with Ruby  

3. cmd cd 到你的網頁所在位置  

4. 執行bundle exec jekyll server 即可預覽，預設port為4000  

5. (加選)可安裝Github Desktop 圖形化介面

6. 更改你的Blog內容  
此處以我使用的 Blog 樣式作範例  
```
layout: 分類
title: '標題'
date: 日期(格式必須為YYYY-MM-DD HH:MM:SS)
categories: 分類
tags: study
image: '是否放入圖片'
lead_text: '網頁描述'
```  

7. Jekyll 網站架構  
``` 
_data/global.yml  # 網站的基本設定資料
_includes/  # 存放網站中會重複使用的HTML檔
_layouots/  # 存放各頁面的HTMML檔
_posts/  # 在此處撰寫Markdowm文件(也可以加上一些基本的HTML和JS)，Jekyll會自動讀取顯示成文章
```
p.s. Markdown語法要換行要在結尾的部分空兩格  
8. 完成後記得上傳到Github  

9. 成功了~


### 建立留言板
1. 到[Disqus](https://disqus.com/)進行註冊  
![](https://i.imgur.com/mpAsfff.png)

2. 修改 _config.yml 檔  
![](https://i.imgur.com/5QLjzmT.png)  

3. 在想顯示留言的內容下方加上下列程式    
(在這裡貼上code會出現排版錯誤，下面列出如何取得這段程式碼)
* 進入Disqus官網，並登入  
![](https://i.imgur.com/5peiYLJ.png)
* 點選  
![](https://i.imgur.com/4C3lgAa.png)  
* 複製這段程式碼到要顯示的位置  
![](https://i.imgur.com/m8GLIaV.png)  

4. 成功了~  
![](https://i.imgur.com/Dx8dg3x.png)




## 故障排除
(在coding的瞬間，我多改了一點，bug不在遙遠 在你身邊~~)
1. could not find ‘bundler’ required by …  
![](https://i.imgur.com/uv8K8KM.png)  
解決方法:  
前提:需先關閉防毒軟體，才可以進行安裝  
安裝:  
*  bundle update –bundler  
*	gem install bundler:1.13.7  
*	gem update –system  
*	執行啟動: bundle exec jekyll server  

2.  jekyll server 報錯
```cmd
/Library/Ruby/Gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:313:in check_for_activated_spec!’: You have already activated public_suffix 3.0.2, but your Gemfile requires public_suffix 3.0.0. Prepending bundle exec to your command may solve this. (Gem::LoadError)
```  
解決方法:    
bundle exec jekyll server  

3.  The page build completed successfully, but returned the following warning for the `main` branch:  
解決方法:  
更改_config.yml  
![](https://i.imgur.com/Xp8uebG.png)  

4. Could not read from remote repository.  
解決方法:  
git remote set-url origin https://github.com/PanteraSama/landingPageResponsive.git  

<font color='red'>可能還有許多種的錯誤，族繁不及備載，請自行Google XD</font>

<hr>


## 參考網址
[Jeykll官方文件](https://jekyllrb.com/docs/)
[Jekyll模板語法](https://gist.github.com/JJediny/a466eed62cee30ad45e2)
[在Winodws上運作jekyll](https://wcc723.github.io/jekyll/2014/01/13/windows-jekyll-server/)
[Github Pages + jekyll 全面介紹極簡搭建個人網站和部落格](https://www.itread01.com/iqhklc.html)





