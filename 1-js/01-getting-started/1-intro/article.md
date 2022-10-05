# JavaScript'ке киришүү

Келгиле, JavaScript'тин өзгөчөлүгү эмнеде экенин, аны менен эмнеге жетише аларыбызды жана аны менен башка кандай технологиялар жакшы иштешин карап көрөлү.

## JavaScript деген эмне?

*JavaScript* башында "веб-баракчаларды жандандыруу" үчүн түзүлгөн.

Бул тилдеги программалар *скрипттер* деп аталат. Алар HTML'де жазылышы мүмкүн жана веб-баракча жүктөлгөн сайын автоматтык түрдө иштетилет.

Скрипттер жөнөкөй текст катары жайылат жана аткарылат. Аларды иштетүү үчүн атайын даярдыктын же компиляциянын кереги жок.

Бул жагынан JavaScript [Java](https://en.wikipedia.org/wiki/Java_(programming_language)) деп аталган башка тилинен абдан айырмаланат.

```smart header="Эмнеге ал <u>Java</u>Script деп аталат?"
JavaScript түзүлүп жатканда "LiveScript" деп аталган. Бирок ошол убакта Java абдан таанымал болгондугунан, жаңы тилди Java'нын "иниси" катары жайгаштыруу пайдалуу болорун чечишкен.

Бирок ал өнүккөн сайын JavaScript [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) деп аталган өзүнүн спецификациясы менен толук өз алдынча тилге айланды жана азыр анын Java менен эч кандай байланышы жок.
```

Бүгүн JavaScript браузерде гана эмес, серверде же [JavaScript кыймылдаткычы](https://en.wikipedia.org/wiki/JavaScript_engine) деп аталган атайын программасы бар каалаган түзмөктө аткарылышы мүмкүн.

Браузерде кээде "JavaScript виртуалдык машинеси" деп аталган орнотулган кыймылдаткычы бар.

Ар кандай кыймылдаткычтардын ар кандай "коддук аттары" бар. Мисалы:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome, Opera жана Edge'де.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox'то.
- ...IE үчүн "Chakra" жана Safari үчүн "JavaScriptCore", "Nitro", "SquirrelFish" ж.б. код аттары бар.

Жогорудагы аталыштарды эстеп калуу жакшы, анткени алар иштеп чыгуучулардын макалаларында көп колдонулат. Биз аларды да колдонобуз. Мисалы, "X функционалдуулугу V8 тарабынан колдоого алынса", анда ал Chrome, Opera жана Edge'де иштеши ыктымал.

```smart header="Кыймылдаткычтар кантип иштейт?"

Кыймылдаткычтар татаал нерсе. Бирок негиздери оңой.

1. Кыймылдаткыч (камтылган, эгер ал браузер болсо) скриптти окуйт ("талдайт").
2. Кийин ал скриптти машине тилине айлантат ("компиляциялайт").
3. Андан кийин машине коду иштетилет жана абдан тез иштейт.

Кыймылдаткыч ар бир этапта оптималдаштырууну колдонот. Жадагалса ал компиляцияланган скриптти иштеп жатканда карап, ал аркылуу өткөн маалыматтарды талдап, алган билиминин негизинде машине кодуна оптималдаштырууларды колдонот. Натыйжада, скрипттер абдан тез иштейт.
```

## JavaScript браузерде эмне кыла алат?

Заманбап JavaScript - бул "коопсуз" программалоо тили. Ал эстутумга же процессорго төмөнкү деңгээлдик кирүүгө мүмкүнчүлүгүн бербейт, анткени ал алгач аны талап кылбаган браузерлер үчүн түзүлгөн.

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

Мындай чектөөлөрдүн мисалдары:

- Веб-баракчадагы JavaScript катуу дисктеги каалаган файлдарды окуй/жаза албайт, аларды көчүрө албайт же программаларды аткара албайт. Анын OS функцияларына түз кирүү мүмкүнчүлүгү жок.

    Заманбап браузерлер ага файлдар менен иштөөгө мүмкүндүк берет, бирок кирүү чектелген жана колдонуучу файлды браузердин терезесине "таштоо" же `<input>` теги аркылуу тандоо сыяктуу аракеттерди жасаганда гана берилет.
    
    Камера/микрофон жана башка түзмөктөр менен иштешүүнүн жолдору бар, бирок алар колдонуучунун ачык уруксатын талап кылат. Ошентип, JavaScript иштетилген баракча веб-камераны тымызын иштетип, айлананы байкап, маалыматты [УКМК](https://en.wikipedia.org/wiki/State_Committee_for_National_Security_(Kyrgyzstan))га жөнөтө албайт.
    There are ways to interact with the camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other page if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must agree for data exchange and must contain special JavaScript code that handles it. We'll cover that in the tutorial.

    This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com`, for example, and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.svg)

Such limitations do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugins/extensions which may ask for extended permissions.

## JavaScript'ти өзгөчө кылган эмне?

Javascript тууралуу кеминде *үч* сонун нерсе бар:

```compare
+ HTML/CSS менен толук интеграция.
+ Жөнөкөй нерселер жөнөкөй жасалат.
+ Бардык негизги браузерлерден колдоого алынат жана демейки боюнча иштетилген.
```
JavaScript - бул үч нерсени бириктирген жалгыз браузер технологиясы.

Бул JavaScript'ти өзгөчө кылат. Ошондуктан бул браузер интерфейстерин түзүүнүн эң кеңири таралган куралы.

Айтор, JavaScript серверлерди, мобилдик тиркемелерди ж.б. түзүү үчүн колдонулат.

## JavaScript'тен "жогору" тилдери

JavaScript'тин синтаксиси бардык муктаждыктарга ылайыктуу эмес. Ар кандай адамдар ар кандай өзгөчөлүктөрдү каалайт.

Муну күтүүгө болот, анткени долбоорлор жана талаптар ар ким үчүн ар кандай.

Ошентип, жакында эле браузерде иштетиле электе JavaScript'ке транспиляцияланган (айландырылган) көптөгөн жаңы тилдер пайда болду.

Заманбап куралдар транспиляцияны абдан ылдам жана мөлтүр кылып, иштеп чыгуучуларга башка тилде код жазууга мүмкүндүк берет жана аны "капкактын астында" автоматтык түрдө которот.

Мындай тилдердин мисалдары:

- [CoffeeScript](https://coffeescript.org/) - бул JavaScript үчүн "синтаксистик кант". Ал кыскараак синтаксисти киргизип, түшүнүктүү жана так код жазууга мүмкүндүк берет. Адатта, Ruby иштеп чыгуучуларына жактырат.
- [TypeScript](https://www.typescriptlang.org/) татаал тутумдарды иштеп чыгууну жана колдоону женилдетүү үчүн "катуу типтештирүүнү" кошууга багытталган. Microsoft'тон иштелип чыккан.
- [Flow](https://flow.org/) деле типтештирүүнү кошот, бирок башкача. Facebook'тан иштелип чыккан.
- [Dart](https://www.dartlang.org/) браузерден тышкары (мисалы, мобилдик тиркемелерде) иштеген өзүнүн кыймылдаткычы бар болгондуктан өзгөчөлөнүп турат. Google'дан иштелип чыккан. 
- [Brython](https://brython.info/) Python'ду JavaScript'ке транспиляциялайт, ал тиркемелерди JavaScript'сиз таза Python тилинде жазууга мүмкүндүк берет.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) - браузерге же түйүнгө багытталган заманбап, кыскартылган жана коопсуз программалоо тили.

Башкалар да бар. Албетте, биз бул тилдердин бирин колдонсок дагы, эмне кылып жатканыбызды чындап түшүнүү үчүн JavaScript'ти билишибиз керек.

## Корутунду

- JavaScript башында браузер үчүн гана түзүлгөн, бирок азыр ал көптөгөн башка чөйрөлөрдө колдонулат.
- Бүгүн JavaScript HTML/CSS менен толук интеграцияланган эң кеңири таралган браузер тили катары өзгөчө орунга ээ.
- JavaScript'ке "которулган" жана кошумча функцияларды камсыз кылган көптөгөн тилдер бар. JavaScript'ти өздөштүргөндөн кийин, жок дегенде кыскача аларды карап чыгуу сунушталат.
