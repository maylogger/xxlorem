# [XXLOREM.js 一用就憤怒的中文假字生產器](http://xxlorem.unfoldgroup.com/)

###關於XXLOREM.js
*XXLOREM.js* 是一款針對 *前端設計師* 打造的 *中文假字生產器*，語料使用[靠北設計師](http://fb.com/kobedesigner) 的匿名靠北內容。我們從中篩選了一些內容，並以程式隨機打亂後重新組合，作為假字使用。

這支 plugin 是以 jQuery 時基礎、以 coffeescript 編寫而成，原始碼請見 `/coffeescripts` 資料夾。


###使用方法
使用時需先引用 jQuery，請在你的網頁加上以下語法：
```
<script src="//code.jquery.com/jquery-1.11.3.min.js"></script>
<script src="//xxlorem.unfoldgroup.com/plugin/xxlorem-1.0.js"></script>
```

XXLOREM.js 提供了兩種方法，讓你可以快速將假字套用到頁面中：
- 方法一：以 jQuery 套用假字於特定物件上
  ```
  $('.example').xxlorem();
  $('.example').xxlorem(3);
  ```
- 方法二：直接在想要填入假字的物件加上 `class="xx"`
  ```
  <p class="xx"></p>
  <p class="xx(3)"></p>
  ```


###參數設置
前述的兩種使用方法，都可以藉由設置不同的參數，來產生不同類型或長度的假字。

採用 方法一 時，您可以用 `$(elment).xxlorem(params)` 方式來設置參數；在 方法二 中，則可以用增加括弧和數值的方式 `<p class="xx(params)"></p>` 來設置參數。

XXLOREM.js 提供了多種類型的假字如下：
- 文字
  - 參數語法：`word` , `words`
  - 參數簡寫：`w`
  - 說明：產生一個或多個文字
  - 範例：`$(ele).xxlorem('10w');` , `<p class="xx(10 words)"><p>`
- 句子
  - 參數語法：`sentence` , `sentences`
  - 參數簡寫：`s`
  - 說明：產生一個或多個句子
  - 範例：`$(ele).xxlorem(3,'sentences');` , `<p class="xx(3s)"><p>`
- 段落
  - 參數語法：`paragraph` , `paragraphs`
  - 參數簡寫：`p`
  - 說明：產生一個或多個段落文字
  - 範例：`$(ele).xxlorem('4p','<br><br>');` , `<p class="xx(4,paragraphs)"><p>`
- 姓名
  - 參數語法：`name`
  - 參數簡寫：`n`
  - 說明：產生一個假姓名
  - 範例：`$(ele).xxlorem('name');` , `<p class="xx(n)"><p>`
- 姓
  - 參數語法：`last name`
  - 參數簡寫：`ln`
  - 說明：產生一個假姓氏
  - 範例：`$(ele).xxlorem('last-name');` , `<p class="xx(ln)"><p>`
- 名
  - 參數語法：`first name`
  - 參數簡寫：`fn`
  - 說明：產生一個假名字
  - 範例：`$(ele).xxlorem('fn');` , `<p class="xx(first name)"><p>`
- 姓名(拼音)
  - 參數語法：`name pinyin`
  - 參數簡寫：`np`
  - 說明：產生一個拼音假姓名
  - 範例：`$(ele).xxlorem('name_pinyin');` , `<p class="xx(np)"><p>`
- 姓(拼音)
  - 參數語法：`last name pinyin`
  - 參數簡寫：`lnp`
  - 說明：產生一個拼音假姓氏
  - 範例：`$(ele).xxlorem('last name pinyin');` , `<p class="xx(lnp)"><p>`
- 名(拼音)
  - 參數語法：`first name pinyin`
  - 參數簡寫：`fnp`
  - 說明：產生一個拼音假名字
  - 範例：`$(ele).xxlorem('first name pinyin');` , `<p class="xx(fnp)"><p>`
- Email
  - 參數語法：`email` , `mail`
  - 參數簡寫：`e` , `m`
  - 說明：產生一個假 email
  - 範例：`$(ele).xxlorem('mail');` , `<p class="xx(m)"><p>`


###參考與傳承
* [zh-lorem](https://github.com/gugod/zh-lorem)
* [MoreText.js: 一用就愛上的中文假文產生器](http://more.handlino.com/)
* [lorem-cn](https://github.com/webzhao/lorem-cn)
* [亂數假文產生器 Chinese Lorem Ipsum](http://www.richyli.com/tool/loremipsum/)


###COPYRIGHT
Copyright © 2015 Unfoldgroup
