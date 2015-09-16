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
方法一：以 jQuery 套用假字於特定物件上
```
$('.example').xxlorem();
$('.example').xxlorem(3);
$('.example').xxlorem('10w');
$('.example').xxlorem('3-5','p');
```

方法二：直接在想要填入假字的物件加上 `class="xx"`
```
<p class="xx"></p>
<p class="xx(3)"></p>
<p class="xx(10w)"></p>
<p class="xx(3-5,p)"></p>
```

注意：當你在使用像 Slim 這類的樣板語言編寫頁面時，可能無法以圓括號的方式添加參數，但是好家在，XXLOREM.js 兼容以「- (減號)」或「_ (底線)」作為參數的串接符號：
```
<p class="xx-5"></p>
<p class="xx_3_p"></p>
<p class="xx-name"></p>
```


###參數設置
前述的兩種使用方法，都可以藉由設置不同的參數，來產生不同類型或長度的假字。

採用 方法一 時，您可以用 `$(elment).xxlorem(params)` 方式來設置參數；在 方法二 中，則可以用增加括弧和數值的方式 `<p class="xx(params)"></p>` 來設置參數。

XXLOREM.js 提供了多種類型的假字如下：
- 文字
  - 參數名：`word` , `words`
  - 簡寫：`w`
  - 說明：產生一個或多個文字
  - 範例：`$(ele).xxlorem('10w');` , `<p class="xx(10 words)"><p>`
- 句子
  - 參數名：`sentence` , `sentences`
  - 簡寫：`s`
  - 說明：產生一個或多個句子
  - 範例：`$(ele).xxlorem(3,'sentences');` , `<p class="xx(3s)"><p>`
- 段落
  - 參數名：`paragraph` , `paragraphs`
  - 簡寫：`p`
  - 說明：產生一個或多個段落文字
  - 範例：`$(ele).xxlorem('4p','<br><br>');` , `<p class="xx(4,paragraphs)"><p>`
- 姓名
  - 參數名：`name`
  - 簡寫：`n`
  - 說明：產生一個假姓名
  - 範例：`$(ele).xxlorem('name');` , `<p class="xx(n)"><p>`
- 姓
  - 參數名：`last-name`
  - 簡寫：`ln`
  - 說明：產生一個假姓氏
  - 範例：`$(ele).xxlorem('last-name');` , `<p class="xx(ln)"><p>`
- 名
  - 參數名：`first-name`
  - 簡寫：`fn`
  - 說明：產生一個假名字
  - 範例：`$(ele).xxlorem('fn');` , `<p class="xx(first-name)"><p>`
- 姓名(拼音)
  - 參數名：`name-pinyin`
  - 簡寫：`np`
  - 說明：產生一個拼音假姓名
  - 範例：`$(ele).xxlorem('name-pinyin');` , `<p class="xx(np)"><p>`
- 姓(拼音)
  - 參數名：`last-name-pinyin`
  - 簡寫：`lnp`
  - 說明：產生一個拼音假姓氏
  - 範例：`$(ele).xxlorem('last-name-pinyin');` , `<p class="xx(lnp)"><p>`
- 名(拼音)
  - 參數名：`first-name-pinyin`
  - 簡寫：`fnp`
  - 說明：產生一個拼音假名字
  - 範例：`$(ele).xxlorem('first-name-pinyin');` , `<p class="xx(fnp)"><p>`
- Email
  - 參數名：`email` , `mail`
  - 簡寫：`e` , `m`
  - 說明：產生一個假 email
  - 範例：`$(ele).xxlorem('mail');` , `<p class="xx(m)"><p>`

通常來說，只需用一個參數就可以完成設置假字的類型或長度 (or range)；或者，你也可以用縮寫的方式，同時設置假字類型和長度（例如 `xx(3p)` 會產生 3 個段落）：

- Javascript
```
$(elment).xxlorem('name');
$(elment).xxlorem(5);
$(elment).xxlorem('10w');
```

- Inline html (注意：直接寫在 HTML 標籤中，參數前後不需 `'` 或 `"` 引號！)
```
<span class="xx(email)"></span>
<span class="xx(lnp)"></span>
<span class="xx(3p)"></span>
```

當你要需要產生多個文字、句子或段落時，則可以使用 2 個參數來設置假字類型和長度 (or range)，請以逗號隔開參數，*參數順序不影響結果*：

- Javascript
```
$(elment).xxlorem('sentences', 10);
$(elment).xxlorem('3-5', 'p');
```

- Inline html（注意：直接寫在 HTML 標籤時，逗號前後請勿留空白符號！）
```
<span class="xx(words,10-20)"></span>
<p class="xx(3,p)"></p>
```

在產生段落 (paragraphs) 時，可彈性的使用第三個參數。
第三個參數為設置換行符號，預設的換行符號為 `\n\n`，可依照需求替換，例如：
```
$(elment).xxlorem('3-5', 'paragraphs', '<br><br>');=
<p class="xx(3-5,p,<hr>)"></p>
```

除非要產生隨機長度的假字，否則我們建議以縮寫、僅使用兩個參數的方式設置段落：
```
$(elment).xxlorem('3p', '<br><br>');
<p class="xx(6p,<hr>)"></p>
```

###參考與傳承
* [zh-lorem](https://github.com/gugod/zh-lorem)
* [MoreText.js: 一用就愛上的中文假文產生器](http://more.handlino.com/)
* [lorem-cn](https://github.com/webzhao/lorem-cn)
* [亂數假文產生器 Chinese Lorem Ipsum](http://www.richyli.com/tool/loremipsum/)


###COPYRIGHT
Copyright © 2015 Unfoldgroup
