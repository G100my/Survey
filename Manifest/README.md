## Manifest.json 是什麼? ##

Manifest.json 可以把它視為
一個能告訴瀏覽器（以下簡稱 UA）你的 web application（以下稱 web app） 要怎麼呈現、
或者要怎麼**安裝** 你的 web app 的 JSON檔案。
普遍應用於 PWA。
一般瀏覽器都能使用 add to Home screen 的功能，
把網址存成書籤放在 Home screen 上，
藉由 manifest.json 可以控制這項操作的細節。
較基本、常用的 member ：

* [name](https://w3c.github.io/manifest/#name-member)
* [short_name](https://w3c.github.io/manifest/#short_name-member)
* [icons](https://w3c.github.io/manifest/#icons-member)
* [display](https://w3c.github.io/manifest/#display-member)
* [start_url](https://w3c.github.io/manifest/#start_url-member)
* [theme_color](https://w3c.github.io/manifest/#theme_color-member)
* [background_color](https://w3c.github.io/manifest/#background_color-member)

### 就以上七個 member 做這次的 Test page ###

* name 和 short_name 可以擇一，通常會在沒辦法完整顯示 name 的時候，會使用 short_name 來顯示，
	例如: Splash screen（啟動 web app 後讀取資料的過場畫面） 會使用 name、Home screen icon 底下的 APP 會用 short_name。
	參考資料: [W3C - 2.2 Application's name](https://w3c.github.io/manifest/#application-s-name)
* display 有四種模式: fullscreen、standalone、minimal-ui、browser。
	如果要讓 web app 的畫面看起來像 Native app 請使用 standalone。
* icons 通常會準備幾種不一樣大小的圖檔，
	以應用於不同螢幕尺寸的 mobile device or desktop，在哪種大小的 device 上採用多大的圖檔取決於 UA。
* 如果 member 的值沒有在 manifest.json，會由 UA 判別，UA 或許會從其他地方補入，判斷是否可以安裝 web app 結果取決於 UA。
	參考 [Installable web applications](https://w3c.github.io/manifest/#installable-web-applications)
	> At any time, the user agent MAY perform the steps to determine installability of the document:
	> 1. Let manifest and manifest URL be the result of obtaining the manifest.
	> 2. If obtaining the manifest results in an error, the user agent MAY either:
	> 	1. Fall back to using the top-level browsing context Document's metadata to to populate manifest in a user-agent-specific way(e.g., setting manifest.name to the document title) and considering the document installable.
	> 	2. Or, consider the document not installable.
	> 3. Otherwise, the Document MAY be considered installable (at the user agent's discretion; see § 2.6 Installability signals ).

更多 manifest - mamber 細節參考 [W3C - web application Manifest -- WebAppManifest dictionary](https://w3c.github.io/manifest/#webappmanifest-dictionary)