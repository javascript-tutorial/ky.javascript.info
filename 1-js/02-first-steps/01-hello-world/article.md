# Салам, дүйнө!

Колдонмонун бул бөлүгүндө биз JavaScript'тин, тилдин өзүн үйрөнөбүз.

Бирок скрипттерди жүргүзүү үчүн бизге иштөө чөйрөсү керек жана бул китеп онлайн болгондуктан, браузер жакшы тандоо болмок. Эгер сиз башка чөйрөгө (мисалы, Node.js) көңүл топтоону пландап жатсаңыз, браузерге тиешелүү буйруктарга убакыт коротпооңуз үчүн, биз алардын көлөмүн (мисалы, `alert`) минималдаштырып коёбуз. Колдонмонун [кийинки бөлүгүндө](/ui) браузердеги JavaScript'ке көңүл бурабыз.

Ошентип, адегенде баракта скриптти кантип аткарууну карап көрөлү. Сервер чөйрөлөрү үчүн (мисалы, Node.js) `"node my.js"` сыяктуу буйрук менен скриптти аткарсаңыз болот. Браузер үчүн бир аз башкача.

## "script" теги

JavaScript программаларын HTML документинин каалаган жерине `<script>` теги менен киргизүүгө болот.

Мисалы үчүн:

```html run height=100
<!DOCTYPE HTML>
<html>

<body>

  <p>Скрипттен мурун...</p>

*!*
  <script>
    alert( 'Салам, дүйнө!' );
  </script>
*/!*

  <p>...Скрипттен кийин.</p>

</body>

</html>
```

```online
Жогорудагы кутучанын жогорку оң бурчундагы "Play" баскычын басуу менен мисалды жүргүзө аласыз.
```

`<script>` теги JavaScript кодун камтыйт, браузер аны иштеп чыгарганда ал автоматтык түрдө аткарылат.

## Заманбап белгилөө

`<script>` теги азыркы учурда сейрек колдонулган, бирок эски коддон дагы эле табыла турган бир нече атрибуттарга ээ:

`type` атрибуту: <code>&lt;script <u>type</u>=...&gt;</code>
: The old HTML standard, HTML4, required a script to have a `type`. Usually it was `type="text/javascript"`. It's not required anymore. Also, the modern HTML standard totally changed the meaning of this attribute. Now, it can be used for JavaScript modules. But that's an advanced topic, we'll talk about modules in another part of the tutorial.

`language` атрибуту: <code>&lt;script <u>language</u>=...&gt;</code>
: This attribute was meant to show the language of the script. This attribute no longer makes sense because JavaScript is the default language. There is no need to use it.

Скрипттерге чейинки жана кийинки комментарийлер.
: Абдан байыркы китептерде жана колдонмолордо сиз `<script>` тегинин ичинен комментарийлерди таба аласыз, мисалы:

    ```html no-beautify
    <script type="text/javascript"><!--
        ...
    //--></script>
    ```

    This trick isn't used in modern JavaScript. These comments hide JavaScript code from old browsers that didn't know how to process the `<script>` tag. Since browsers released in the last 15 years don't have this issue, this kind of comment can help you identify really old code.


## Тышкы скрипттер

Эгерде бизде JavaScript коду көп болсо, биз аны бөлөк файлга сала алабыз.

Скрипт файлын HTML'ге `src` атрибуту аркылуу кошууга болот:

```html
<script src="/path/to/script.js"></script>
```

Here, `/path/to/script.js` is an absolute path to the script from the site root. One can also provide a relative path from the current page. For instance, `src="script.js"`, just like `src="./script.js"`, would mean a file `"script.js"` in the current folder.

Биз толук URL дарегин да бере алабыз. Мисалы үчүн:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```

Бир нече скрипттерди кошуу үчүн бир нече тегдерди колдонуңуз:

```html
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
```

```smart
As a rule, only the simplest scripts are put into HTML. More complex ones reside in separate files.

The benefit of a separate file is that the browser will download it and store it in its [cache](https://en.wikipedia.org/wiki/Web_cache).

Other pages that reference the same script will take it from the cache instead of downloading it, so the file is actually downloaded only once.

That reduces traffic and makes pages faster.
```

````warn header="If `src` is set, the script content is ignored."
A single `<script>` tag can't have both the `src` attribute and code inside.

Төмөндөгү мисал иштебейт:

```html
<script *!*src*/!*="file.js">
  alert(1); // мазмунуна көңүл бурулбайт, анткени src атрибуту бар
</script>
```

Биз же тышкы `<script src="...">` скриптти, же `<script>` тегинин ичиндеги кадимки кодду тандашыбыз керек.

Жогорудагы мисалды эки скриптке бөлсө болот:

```html
<script src="file.js"></script>
<script>
  alert(1);
</script>
```
````

## Корутунду

- Биз баракчага JavaScript кодун кошуу үчүн `<script>` тегин колдоно алабыз.
- `type` жана `language` атрибуттары талап кылынбайт.
- Тышкы файлдагы скрипт `<script src="path/to/script.js"></script>` менен киргизилиши мүмкүн.

There is much more to learn about browser scripts and their interaction with the webpage. But let's keep in mind that this part of the tutorial is devoted to the JavaScript language, so we shouldn't distract ourselves with browser-specific implementations of it. We'll be using the browser as a way to run JavaScript, which is very convenient for online reading, but only one of many.
