# JavaScript'ке кирүү

Келгиле, JavaScript'тин өзгөчөлүгү эмнеде экенин, аны менен эмнеге жетише аларыбызды жана аны менен кандай башка технологиялар жакшы ойноорун карап көрөлү.

## JavaScript деген эмне?

*JavaScript* башында "веб-баракчаларды жандандыруу" үчүн түзүгөн.

Бул тилдеги программалар *скрипттер* деп аталат. Алар HTML'де жазылышы мүмкүн жана веб-баракча жүктөлгөн сайын автоматтык түрдө иштетилет.

Скрипттер жөнөкөй текст катары жайылат жана аткарылат. Аларды иштетүү үчүн атайын даярдыктын же компиляциянын кереги жок.

Бул жагынан JavaScript [Java](https://en.wikipedia.org/wiki/Java_(programming_language)) деп аталган башка тилинен абдан айырмаланат.

```smart header="Эмнеге ал <u>Java</u>Script деп аталат?"
JavaScript түзүлгөндө, анын башка "LiveScript" деген аталышы болгон. Бирок Java ошол убакта абдан популярдуу болгондугунан, жаңы тилди Java тилинин "кичүү иниси" катары жайгаштыруу пайдалуу болорун чечишкен.

Бирок ал өнүккөн сайын JavaScript [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) деп аталган өзүнүн спецификациясы менен толук өз алдынча тил болуп калды жана азыр анын Java менен эч кандай байланышы жок.
```

Бүгүн JavaScript браузерде гана эмес, серверде же чындыгында [JavaScript кыймылдаткычы](https://en.wikipedia.org/wiki/JavaScript_engine) деп аталган атайын программасы бар каалаган түзмөктө аткарылышы мүмкүн.

Браузерде кээде "JavaScript виртуалдык машинеси" деп аталган орнотулган кыймылдаткычы бар.

Ар кандай кыймылдаткычтардын ар кандай "коддук аттары" бар. Мисалы:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome, Opera жана Edge'де.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox'то.
- ...IE үчүн "Chakra" жана Safari үчүн "JavaScriptCore", "Nitro", "SquirrelFish" ж.б. код аттары бар.

Жогорудагы аталыштарды эстеп калуу жакшы, анткени алар иштеп чыгуучулардын макалаларында көп колдонулат. Биз аларды да колдонобуз. Мисалы, "X функционалдуулугу V8 тарабынан колдоого алынса", анда ал Chrome, Opera жана Edge'де иштеши мүмкүн.

```smart header="Кыймылдаткычтар кантип иштейт?"

Кыймылдаткычтар татаал нерсе. Бирок негиздери оңой.

1. Кыймылдаткыч (камтылган, эгер ал браузер болсо) скриптти окуйт ("талдайт").
2. Кийин ал скриптти машине тилине айлантат ("компиляциялайт").
3. Андан кийин машине коду иштетилет жана абдан тез иштейт.

Кыймылдаткыч ар бир этапта оптималдаштырууну колдонот. Ал тургай, ал компиляцияланган скриптти иштеп жатканда карап, ал аркылуу өткөн маалыматтарды талдап, алган билиминин негизинде машине кодуна оптималдаштырууларды колдонот. Натыйжада, скрипттер абдан тез иштейт.
```

## JavaScript браузерде эмне кыла алат?

Заманбап JavaScript - бул "коопсуз" программалоо тили. Ал эстутумга же процессорго төмөнкү деңгээлде кирүү мүмкүнчүлүгүн камсыз кылбайт, анткени ал алгач аны талап кылбаган браузерлер үчүн түзүлгөн.

JavaScript'тин мүмкүнчүлүктөрү ал иштеген чөйрөгө өтө көз каранды. Мисалы, [Node.js](https://wikipedia.org/wiki/Node.js) ыктыярдуу файлдарды окууга/жазууга, тармак сурамдарын аткарууга ж.б. функцияларды колдойт.

Браузердеги JavaScript веб-баракчаны манипуляциялоого, колдонуучу менен өз ара аракеттешүүгө жана веб-серверге байланыштуу баарын жасай алат.

Мисалы:

- Баракчага жаңы HTML-кодду кошуу, учурдагы мазмунду өзгөртүү, стилдерди өзгөртүү.
- Колдонуучунун аракетине, чычкандын чыкылдатканына, көрсөткүчтүн кыймылына, баскычтын басуусуна.
- Тармак аркылуу алыскы серверлерге сурамдарды жөнөтүү, файлдарды жүктөп алуу жана жүктөө ([AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) жана [COMET](https://en.wikipedia.org/wiki/Comet_(программалоо)) технологиялары).
- Кукилерди алуу жана орнотуу, келүүчүгө суроолорду берүү, билдирүүлөрдү көрсөтүү.
- Кардар тараптагы берилмелерди эстеп калуу ("local storage").

## Браузердеги JavaScript эмне кыла АЛБАЙТ?

JavaScript'тин браузердеги мүмкүнчүлүктөрү колдонуучунун коопсуздугун коргоо үчүн чектелген. Максаты - жаман веб-баракчанын жеке маалыматка кирүүсүнө же колдонуучунун маалыматтарына зыян келтирүүгө жол бербөө.

Мындай чектөөлөрдүн мисалдары кирет:

- Веб-баракчадагы JavaScript катуу дисктеги каалаган файлдарды окуй/жаза албайт, аларды көчүрө албайт же программаларды аткара албайт. Анын OS функцияларына түз кирүү мүмкүнчүлүгү жок.

    Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like "dropping" a file into a browser window or selecting it via an `<input>` tag.

    There are ways to interact with the camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other page if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must agree for data exchange and must contain special JavaScript code that handles it. We'll cover that in the tutorial.

    This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com`, for example, and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.svg)

Such limitations do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugins/extensions which may ask for extended permissions.

## What makes JavaScript unique?

There are at least *three* great things about JavaScript:

```compare
+ Full integration with HTML/CSS.
+ Simple things are done simply.
+ Supported by all major browsers and enabled by default.
```
JavaScript is the only browser technology that combines these three things.

That's what makes JavaScript unique. That's why it's the most widespread tool for creating browser interfaces.

That said, JavaScript can be used to create servers, mobile applications, etc.

## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So, recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it "under the hood".

Examples of such languages:

- [CoffeeScript](https://coffeescript.org/) is "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](https://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](https://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.

There are more. Of course, even if we use one of these transpiled languages, we should also know JavaScript to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but it is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language, fully integrated with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
