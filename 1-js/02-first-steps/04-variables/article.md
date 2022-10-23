# Өзгөрмөлөр

Көпчүлүк учурда, JavaScript тиркемеси маалымат менен иштеши керек. Бул жерде эки мисал келтирилген:
1. Интернет-дүкөн -- маалымат сатылуучу буюмдарды жана соода себетин камтышы мүмкүн.
2. Баарлашуу тиркемеси -- маалымат колдонуучуларды, билдирүүлөрдү ж.б. көптөгөн нерселерди камтышы мүмкүн.

Өзгөрмөлөр бул маалыматтарды сактоо үчүн колдонулат.

## Өзгөрмө

[Өзгөрмө](https://en.wikipedia.org/wiki/Variable_(computer_science)) -- бул берилмелер үчүн "аталган сактагыч". Биз товарларды, келүүчүлөрдү жана башка берилмелерди сактоо үчүн өзгөрмөлөрдү колдоно алабыз.

JavaScript'те өзгөрмө түзүү үчүн, `let` ачкыч сөзүн колдонуңуз.

Төмөнкү нускама "билдирүү" аталышы менен өзгөрмө түзөт (башкача айтканда: *жарыялайт*):

```js
let message;
```

Эми `=` өздөштүрүү оператору аркылуу ага берилмелерди киргизе алабыз:

```js
let message;

*!*
message = 'Hello'; // 'Hello' сабын message деп аталган өзгөрмөдө сактоо
*/!*
```

Сап эми өзгөрмө менен байланышкан эстутум аймагына сакталат. Биз ага өзгөрмө аты менен кире алабыз:

```js run
let message;
message = 'Hello!';

*!*
alert(message); // өзгөрмөнүн мазмунун көрсөтөт
*/!*
```

Кыскача айтканда, биз өзгөрмөнүн жарыялоосун жана берилмелерди жазууну бир сапка бириктире алабыз:

```js run
let message = 'Hello!'; // өзгөрмөнү аныктайбыз жана ага маанисин беребиз

alert(message); // Hello!
```

We can also declare multiple variables in one line:

```js no-beautify
let user = 'John', age = 25, message = 'Hello';
```

Мындай ыкма кыскараак көрүнүшү мүмкүн, бирок биз муну сунуштабайбыз. Жакшыраак окулушу үчүн, ар бир өзгөрмөнү жаңы сапта жарыялаңыз.

Көп саптуу версиясы бир аз узунураак, бирок окууга оңоюраак:

```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

Кээ бир адамдар бир нече өзгөрмөлөрдү мындай көп саптуу стилинде аныкташат:

```js no-beautify
let user = 'John',
  age = 25,
  message = 'Hello';
```

...Же жадагалса саптын башында үтүр менен:

```js no-beautify
let user = 'John'
  , age = 25
  , message = 'Hello';
```

Негизинен, бул варианттардын баары бирдей иштейт. Демек, бул жеке табит жана эстетика маселеси.

````smart header="`let` ордуна `var`"
Эски скрипттерде дагы башка, `let` ордуна `var` ачкыч сөзүн таба аласыз:

```js
*!*var*/!* message = 'Hello';
```

`var` ачкыч сөзү `let` менен *дээрлик* бирдей. Ал өзгөрмөнү жарыялайт, бирок бир аз башкача, "эскирген" жол менен.

`let` жана `var` ортосунда тымызын айырмачылыктар бар, бирок алар биз үчүн азырынча маанилүү эмес. Биз аларды <info:var> бөлүмүндө кененирээк карап чыгабыз.
````

## Жашоодон алынган аналогия

Эгерде өзгөрмөнү берилмелер үчүн уникалдуу аталышы бар "куту" катары элестетсек, биз "өзгөрмө" түшүнүгүн оңой эле түшүнө алабыз.

Мисалы үчүн, `message` өзгөрмөсүн `"message"` деп аталган жана анын ичиндеги `"Hello!"` мааниси бар куту катары элестетүүгө болот.

![](variable.svg)

Биз кутуга ар кандай маанини сала алабыз.

Ошондой эле биз аны каалаганча көп жолу өзгөртө алабыз:

```js run
let message;

message = 'Hello!';

message = 'World!'; // мааниси өзгөртүлдү

alert(message);
```

Маани өзгөртүлгөндө, эски берилмелер өзгөрмөдөн жок кылынат:

![](variable-change.svg)

Ошондой эле биз эки өзгөрмөнү жарыялап, берилмелерди биринен экинчисине көчүрө алабыз.

```js run
let hello = 'Hello world!';

let message;

*!*
// hello өзгөрмөсүндөгү 'Hello world' маанисин message өзгөрмөсүнө көчүрөбүз
message = hello;
*/!*

// эми эки өзгөрмө бирдей берилмелерди камтыйт
alert(hello); // Hello world!
alert(message); // Hello world!
```

````warn header="Кайрадан жарыялоо катаны жаратат"
Өзгөрмө бир гана жолу жарыяланышы керек.

Бир эле өзгөрмөнүн кайталанган жарыялоосу ката болуп саналат:

```js run
let message = "Ушул";

// 'let' ачкыч сөзүнүн кайталанышы катага алып келет:
let message = "Ошол"; // SyntaxError: 'message' has already been declared
```
Ошондуктан, биз өзгөрмөнү бир гана жолу жарыялап, ага `let`'сиз кайрылышыбыз керек.
````

```smart header="Функционалдуу тилдер"
Өзгөрмө маанилерин өзгөртүүгө тыюу салган [Scala](http://www.scala-lang.org/) же [Erlang](http://www.erlang.org/) сыяктуу [функционалдуу](https://en.wikipedia.org/wiki/Functional_programming) программалоо тилдери бар экенин белгилей кетүү кызык.

Мындай тилдерде бир жолу "кутуда" сакталган маани түбөлүккө ошол жерде калат. Эгер башка нерсени сактоо керек болсо, тил бизди жаңы кутуча түзүүгө (жаңы өзгөрмө жарыялоого) мажбурлайт. Биз эски өзгөрмөнү колдоно албайбыз.

Бир караганда бул бир аз кызыктай көрүнгөнү менен, бул тилдер олуттуу иштеп чыгууга жөндөмдүү. Мындан тышкары, бул чектөө кээ бир артыкчылыктарды берген параллелдүү эсептөөлөр сыяктуу аймактар бар. Мындай тилди үйрөнүү (сиз аны жакында колдонууну пландабасаңыз да) акыл-эсти кеңейтүү үчүн сунушталат.
```

## Өзгөрмөлөрдү атоо [#variable-naming]

JavaScript'те өзгөрмө аттарына эки чектөө бар:

1. Өзгөрмөнүн аты тамгаларды, сандарды же `$` жана `_` белгилерин гана камтышы керек.
2. Биринчи символ сан болбошу керек.

Жарактуу аттардын мисалдары:

```js
let userName;
let test123;
```

Аты бир нече сөздү камтыса, көбүнчө [төө нотациясы](https://en.wikipedia.org/wiki/CamelCase) колдонулат. Башкача айтканда, сөздөр бири-бирин ээрчийт, анда ар бир кийинки сөз баш тамга менен башталат: `myVeryLongName`.

Эң кызыгы -- аттарда доллар белгиси `'$'` жана ылдыйкы сызыкча `'_'` да колдонулушу мүмкүн. Алар тамгалар сыяктуу эч кандай өзгөчө мааниси жок кадимки белгилер.

Бул аттар жарактуу:

```js run untrusted
let $ = 1; // "$" аты менен өзгөрмө жарыяланды
let _ = 2; // ал эми "_" аты менен өзгөрмө

alert($ + _); // 3
```

Туура эмес өзгөрмө аттарынын мисалдары:

```js no-beautify
let 1a; // сан менен башталуу мүмкүн эмес

let my-name; // атта '-' дефисти коюуга болбойт
```

```smart header="Регистр маанилүү"
`apple` жана `APPLE` деп аталган өзгөрмөлөр -- бул эки башка өзгөрмө.
```

````smart header="Латын эмес тамгаларга уруксат берилет, бирок сунушталбайт"
Каалаган тилди, анын ичинде кирил тамгаларын же жадагалса иероглифтерди колдонууга болот:

```js
let аталыш = '...';
let 我 = '...';
```

Техникалык жактан бул жерде ката жок. Мындай аттарга уруксат берилген, бирок өзгөрмө аттарында англис тилин колдонуу боюнча эл аралык келишим бар. Кичинекей скрипт жазып жатсак да, анын алдында өмүрү узун болушу мүмкүн. Башка өлкөлөрдөн келгендер аны бир нече жолу окууга туура келиши мүмкүн.
````

````warn header="Резервделген аттар"
[Резервделген сөздөрдүн тизмеси](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) бар. Аларды өзгөрмө аттары катары колдонууга болбойт, анткени алар тилдин өзү тарабынан колдонулат.

Мисалы: `let`, `class`, `return`, жана `function` резервделген.

Төмөндөгү код синтаксис катасын жаратат:

```js run no-beautify
let let = 5; // өзгөрмөнү "let" деп атоого болбойт, ката!
let return = 5; // ошондой эле "return" деп атоого болбойт, ката!
```
````

````warn header="`use strict` колдонбостон өзгөрмө түзүү"

Адатта, биз өзгөрмөнү колдонуудан мурун аны аныкташыбыз керек. Бирок мурда `let` колдонбостон, жөн гана маани берүү менен өзгөрмө түзүүгө техникалык жактан мүмкүн болгон. Эски скрипттер менен шайкештикти сактоо үчүн скрипттерибизге `use strict` иштетпесек да, бул азыр деле иштейт.

```js run no-strict
// эсбелги: бул мисалда "use strict" колдонулбайт

num = 5; // "num" өзгөрмөсү мурда жок болгондо, ал түзүлөт

alert(num); // 5
```

Бул жаман тажрыйба, ал катуу режиминде катага алып келет:

```js
"use strict";

*!*
num = 5; // ката: num is not defined
*/!*
```
````

## Константалар

Константа (өзгөрүлбөс) өзгөрмөнү жарыялоо үчүн, `let` ордуна `const` колдонуңуз:

```js
const myBirthday = '18.04.1982';
```

`const` аркылуу жарыяланган өзгөрмөлөр "константалар" деп аталат. Аларды өзгөртүүгө болбойт. Мындай кылуу аракети катага алып келет:

```js run
const myBirthday = '18.04.1982';

myBirthday = '01.01.2001'; // ката, константаны өзгөртүүгө болбойт!
```

Эгерде программист өзгөрмө эч качан өзгөрбөйт деп ишенсе, ал муну кепилдей алат жана аны `const` аркылуу жарыялоо менен ар бирине так кабарлай алат.

### Баш тамгадагы константалар

Скрипт аткарылганга чейин белгилүү болгон эстеп калууга кыйын маанилер үчүн константаларды тергеме ат катары колдонуу тажрыйбасы кеңири таралган.

Мындай константалардын аталыштары баш тамгалар жана ылдыйкы сызыкчалар менен жазылат.

Мисалы, "он алтылык форматта" ар кандай түстөр үчүн константаларды жасайлы:

```js run
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...түстү тандоо керек болгондо
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

Артыкчылыктары:

- `"#FF7F00"` дегенге караганда `COLOR_ORANGE` эстеп калуу далай оңоюраак.
- `"#FF7F00"` киргизүүдө ката кетирүү `COLOR_ORANGE` киргизүүгө караганда далай оңоюраак.
- Кодду окуп жатканда `#FF7F00` дегенге караганда `COLOR_ORANGE` далай түшүнүктүүрөөк болот.

Качан константа үчүн баш тамгаларды колдонушубуз керек жана качан аны кадимкидей аташыбыз керек? Келгиле, бул маселени чечели.

"Константа" болуу жөн гана өзгөрмөнүн мааниси эч качан өзгөрбөй турганын билдирет. Бирок аткарылганга чейин белгилүү болгон константалар бар (кызыл түстүн он алтылык мааниси сыяктуу) жана скрипттин аткарылышы учурунда *эсептелүүчү*, бирок алар башында жарыялангандан кийин өзгөрбөй турган константалар да бар.

Мисалы үчүн:

```js
const pageLoadTime = /* веб-баракчаны жүктөөгө сарпталган убакыт */;
```

The value of `pageLoadTime` is not known prior to the page load, so it's named normally. But it's still a constant because it doesn't change after assignment.

In other words, capital-named constants are only used as aliases for "hard-coded" values.

## Нерселерди туура атаңыз

Өзгөрмөлөр жөнүндө сөз кыла турган болсок, дагы бир өтө маанилүү нерсе бар.

Өзгөрмөнүн аталышы ал сактаган берилмелерди сыпаттаган таза, анык мааниге ээ болушу керек.

Variable naming is one of the most important and complex skills in programming. A quick glance at variable names can reveal which code was written by a beginner versus an experienced developer.

In a real project, most of the time is spent modifying and extending an existing code base rather than writing something completely separate from scratch. When we return to some code after doing something else for a while, it's much easier to find information that is well-labeled. Or, in other words, when the variables have good names.

Please spend time thinking about the right name for a variable before declaring it. Doing so will repay you handsomely.

Бир нече жакшы эрежелер:

- `userName` же `shoppingCart` сыяктуу окууга оңой аттарды колдонуңуз.
- Эмне кылып жатканыңызды так билбесеңиз, `a`, `b`, `c` сыяктуу кыскартуулардан же кыска аталыштардан алыс болуңуз.
- Make names maximally descriptive and concise. Examples of bad names are `data` and `value`. Such names say nothing. It's only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
- Agree on terms within your team and in your own mind. If a site visitor is called a "user" then we should name related variables `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.

Жөнөкөй угулабы? Indeed it is, but creating descriptive and concise variable names in practice is not. Go for it.

```smart header="Кайрадан колдонуу же жаңы өзгөрмө түзүү?"
And the last note. There are some lazy programmers who, instead of declaring new variables, tend to reuse existing ones.

As a result, their variables are like boxes into which people throw different things without changing their stickers. What's inside the box now? Who knows? We need to come closer and check.

Such programmers save a little bit on variable declaration but lose ten times more on debugging.

Кошумча өзгөрмө - бул жакшылык, жамандык эмес.

Modern JavaScript minifiers and browsers optimize code well enough, so it won't create performance issues. Using different variables for different values can even help the engine optimize your code.
```

## Корутунду

We can declare variables to store data by using the `var`, `let`, or `const` keywords.

- `let` -- бул өзгөрмөнү жарыялоонун заманбап ыкмасы.
- `var` -- бул өзгөрмөнү жарыялоонун эскирген ыкмасы. Normally we don't use it at all, but we'll cover subtle differences from `let` in the chapter <info:var>, just in case you need them.
- `const` -- бул `let` сыяктуу, бирок өзгөрмөнүн маанисин өзгөртүүгө болбойт.

Variables should be named in a way that allows us to easily understand what's inside them.
