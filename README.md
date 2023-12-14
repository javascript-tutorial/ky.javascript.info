# Заманбап JavaScript колдонмосу Кыргыз тилинде 🇰🇬

Бул репозиторийде <https://javascript.info> колдонмосунун кыргыз тилиндеги котормосу сакталып жатат.


**Сиз кантип салым кошо аласыз:**

1. [Kyrgyz Translate Progress](https://github.com/javascript-tutorial/ky.javascript.info/issues/1) талкуулоосун карап көрүңүз.
2. Которгуңуз келген, белгиленбеген макаланы тандаңыз.
3. Ошол эле талкуулоого макаланын аталышы менен жорум кошуңуз, мисалы, `JavaScript'ке киришүү`. Ал макаланы сиз которуп жатканыңызды баары билиши үчүн, биздин ботубуз аны талкуулоодо белгилейт. Сиздин жорумуңуз макаланын аталышын гана камтышы керек.
4. Репозиторийди көчүрүңүз ("Fork" баскычын басыңыз), андан кийин бир макаланы которуп, бүткөндөн кийин, биригүү сурамын жөнөтүңүз (Pull Request). Сурамдын аталышы сиз которгон макаланын аталышына дал келиши керек. Кээ бир макалаларда тапшырмалар, сүрөттөр ж.б. камтылган кошумча файлдар бар. Аларды да которуу керек.

Котормо боюнча суроолоруңуз болсо, котормонун аталышы менен [талкуу (Issue) түзсөңүз болот](https://github.com/javascript-tutorial/ky.javascript.info/issues/new), мисалы: "Translation: Code quality > Debugging in Chrome".

Сиз текстти каалаган редактордо түзөтө аласыз. Бул колдонмо түшүнүүгө оңой болгон кеңейтилген "markdown" форматын колдонот. Ал эми натыйжасын сайтта кандай көрүнөрүн көргүңүз келсе, колдонмону жергиликтүү түрдө иштетүү үчүн анын [сервери бар](https://github.com/javascript-tutorial/server).

Маалымат дагы деле жетишсизби? Кененирээк [бул жерде (орус тилинде)](https://github.com/javascript-tutorial/ru.javascript.info/blob/master/CONTRIBUTING.md) окусаңыз болот. 

Сураныч, салым кошуучуларга котормоңузду карап чыгууга жана бириктирүүгө же өзгөртүүнү талап кылууга уруксат бериңиз.
   
Салым кошуучулар жооп бербесе, же салым кошуучу болгуңуз келсе, бизге [негизги репозиторийге](https://github.com/javascript-tutorial/en.javascript.info/issues/new) жазыңыз. 
    
🎉 Чоң ыракмат!

Котормо жарыяланганда сиздин атыңыз жана салымыңыздын көлөмү "About project" баракчасында көрүнөт.

P.S. Тилдердин толук тизмесин <https://javascript.info/translate> дарегинен тапсаңыз болот.

## Түзүлүшү 📋

Ар бир бөлүм, макала же тапшырма өзүнүн папкасында жайгашкан.

`N-url` деп аталган папка, мында `N` – ылгоо үчүн сан (макалалар иреттелген), ал эми `url` - сайттагы URL аталышы болуп саналат.

Папкада төмөнкү файлдардын бири бар:

- бөлүм үчүн `index.md`,
- макала үчүн `article.md`,
- тапшырманы түзүү үчүн `task.md` (жана ошондой эле анын чечими менен `solution.md`, эгерде бар болсо).

Файл `# Башжазуусу` менен башталат, андан кийин Markdown форматындагы текст болот. Аны жөнөкөй текст редакторунда түзөтүүгө болот.

Макала же тапшырма үчүн кошумча булактар жана мисалдар да ошол эле папкада болот.

## Котормо боюнча кеңештер

Сураныч, саптарды жана абзацтарды "болгондой" калтырыңыз - жаңы саптарды кошпоңуз жана учурдагыларды алып салбаңыз. Келечектеги өзгөртүүлөрдү англисче версиясынан котормого бириктирүүнү жеңилдетет.

Эгерде сиз англис тилиндеги версиясын жакшыртууга болорун көрсөңүз – өтө сонун, анда ага сунуш көрсөтүңүз.

### Терминдер

- Кээ бир спецификация терминдерин которууга болбойт, мис. "Функцияны декларациялоо" "ошол бойдон" калат.
- `resolved promise`, `slash`, `regexp`, жана башка терминдери үчүн глоссарийде карап көрүңүз. Болбосо, [MDN](https://developer.mozilla.org/en-US/) сыяктуу колдонмолордон котормолорду издеңиз.


### Мааниси бар терминдер

In English many terms have an obvious meaning. For a person who doesn't understand English, there's no such meaning.

Please keep that in mind, sometimes explanations or additional translations are needed, e.g.

```md
`ReadableStream` allows to read data chunk-by-chunk.
```

The class name `ReadableStream` has an obvious meaning for those who understand English.

Some people who read translations may not know English so well. So we can add a translation of `ReadableStream` in parentheses, like this (Spanish below):

```md
`ReadableStream` ("flujo legible") permite leer datos fragmento por fragmento. 
```

### Код блокторундагы текст

- Комментарийлерди которуңуз.
- Колдонуучунун билдирүүлөрүн жана мисал саптарын которуңуз.
- Өзгөрмөлөрдү, класстарды, идентификаторлорду которбоңуз.
- Котормодон кийин коддун иштешин текшериңиз :)

Мисалы:

```js
// Example
const text = "Hello, world";
document.querySelector('.hello').innerHTML = text;
```

✅ КЫЛЫҢЫЗ (комментарийди которуңуз):

```js
// Мисал
const text = 'Салам, дүйнө';
document.querySelector('.hello').innerHTML = text;
```

❌ КЫЛБАҢЫЗ (классты которбоңуз):

```js
// Мисал
const text = 'Салам, дүйнө';
// ".hello" бул класстын аталышы
// КОТОРБОҢУЗ
document.querySelector('.салам').innerHTML = text;
```

Please note, that sometimes code is followed by pictures, and if you translate text `Hello` -> `Hola` in the code, you need to translate text in picturess as well.

In that case it's probably easier not to translate such text. See more about translating images later.


### External Links

If an external link is to Wikipedia, e.g. `https://en.wikipedia.org/wiki/JavaScript`, and a version of that article exists in your language that is of decent quality, link to that version instead.

Мисалы:

```md
[JavaScript](https://en.wikipedia.org/wiki/JavaScript) is a programming language.
```

✅ БОЛОТ (en -> ky):

```md
[JavaScript](https://es.wikipedia.org/wiki/JavaScript) бул программалоо тили.
```

MDN шилтемелери үчүн жарым-жартылай которулган версиясы болот.

Шилтемедеги макаланын которулган версиясы жок болсо, шилтемени "ошол бойдон" калтырыңыз.

### Метамаалымат

Кээ бир файлдардын, көбүнчөсү тапшырмалардын жогору жагында `---` менен чектелген YAML метамаалыматы бар:

```md
importance: 5

---
...
```

Сураныч, "importance" (жана башка жогорудагы матамаалыматты) которбоңуз.

### Anchors

Some headers have `[#anchor]` at the end, e.g.

```md
## Spread operator [#spread-operator]
```

Please don't translate or remove the `[#...]` part, it's for URL anchors.


### Images

Most illustrations use SVG format, the text in there can be replaced with a translated variant.

The translated text is in `images.yml` file in the tutorial root.

The file format is YAML:
```yaml
image.svg:        # image file
  "hello world":  # English phrase
    text: "Hola mundo"  # translation
    position: "centre"  # "center" or "right", if needed to center or right-align the translation
```

## Running locally

You can run the tutorial server locally to see how the translation looks.

The server and install instructions are at <https://github.com/javascript-tutorial/server>. 
