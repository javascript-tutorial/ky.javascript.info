# Берилмелер түрлөрү

JavaScript'теги маани ар дайым аныкталган түргө ээ болот. Мисалы, сап же сан.

JavaScript'те сегиз негизги берилмелер түрлөрү бар. Бул бөлүмдө биз аларды жалпысынан карап чыгабыз, ал эми кийинки бөлүмдөрдө ар бири жөнүндө кененирээк сүйлөшөбүз.

Биз өзгөрмөгө ар кандай берилмелер түрүн жарыялай алабыз. Ал жерде бир учурда сап, ал эми башка учурда - сан болушу мүмкүн:

```js
// ката болбойт
let message = "салам";
message = 123456;
```

Муну кылууга жол берген программалоо тилдери "динамикалык типтештирилген" деп аталат. Бул берилмелер түрлөрү бар экенин билдирет, бирок өзгөрмөлөр алардын эч бирине байланган эмес.

## Сан (number)

```js
let n = 123;
n = 12.345;
```

*Number* түрү бүтүн жана жылышма чекиттүү сандарды билдирет.

Сандар үчүн көптөгөн операциялар бар, мис. көбөйтүү `*`, бөлүү `/`, кошуу `+`, кемитүү `-` ж.б.

Кадимки сандардан тышкары, "өзгөчө сандык маанилер" деп аталгандар бар, алар дагы бул берилмелер түрүнө таандык: `Infinity`, `-Infinity` жана `NaN`.

- `Infinity` математикалык [чексиздикти](https://en.wikipedia.org/wiki/Infinity) ∞ билдирет. Бул кандайдыр бир сандан чоңураак өзгөчө маани.

    Биз аны нөлгө бөлүүнүн натыйжасында ала алабыз:

    ```js run
    alert( 1 / 0 ); // Infinity
    ```

    Же аны ачык белгилегенде:

    ```js run
    alert( Infinity ); // Infinity
    ```
- `NaN` эсептөө катасын билдирет. Бул туура эмес же аныкталбаган математикалык операциянын натыйжасы, мисалы:

    ```js run
    alert( "сан эмес" / 2 ); // NaN, мындай бөлүү ката болуп эсептелет
    ```

    `NaN` жабышкак болот. `NaN` менен ар кандай кийинки математикалык операция `NaN` кайтарат:

    ```js run
    alert( NaN + 1 ); // NaN
    alert( 3 * NaN ); // NaN
    alert( "сан эмес" / 2 - 1 ); // NaN
    ```

    Демек, математикалык туюнтманын бир жеринде `NaN` бар болсо, ал бүт натыйжага таралат (бир гана бөтөнчө бар: `NaN ** 0` операциянын натыйжасы `1` болот).

```smart header="Математикалык операциялар коопсуздуу"
JavaScript'те математикалык эсептөөлөр "коопсуздуу". Биз каалаган нерсени кыла алабыз: нөлгө бөлүү, сандык эмес саптарга сандар катары кайрылуу ж.б.

Скрипт эч качан фаталдуу ката менен токтобойт ("өлбөйт"). Эң жаман учурда, биз аткаруунун натыйжасында `NaN` алабыз.
```

Атайын сандык маанилер "number" түрүнө таандык. Албетте, бул сөздүн адаттагы мааниде сандар эмес.

Сандар менен иштөө тууралуу кененирээк <info:number> бөлүмүндө караштырабыз.

## BigInt [#bigint-type]

JavaScript'те "number" түрү <code>(2<sup>53</sup>-1)</code>ден чоңураак (бул `9007199254740991`) же <code>-(2<sup>53</sup>-1)</code>ден кичине бүтүн сандык маанилерди билдире албайт.

Тактап айтканда, "number" түрү чоңураак бүтүн сандарды (<code>1.7976931348623157 * 10<sup>308</sup></code>ге чейин) сактай алат, бирок коопсуз бүтүн сан <code>±(2<sup>53</sup>-1)</code> диапазонунан тышкары тактык катасы болот, анткени бардык сандар туруктуу 64-биттик сактагычка туура келбейт. Ошентип, "болжолдуу" маани сакталышы мүмкүн.

```js
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992
```

Мындайча айтканда, <code>(2<sup>53</sup>-1)</code>ден чоң так бүтүн сандарды "number" тибинде такыр сактоого болбойт.

Көпчүлүк максаттар үчүн <code>±(2<sup>53</sup>-1)</code> диапазону жетиштүү, бирок кээде бизге чыныгы чоң бүтүн сандардын толук диапазону керек болот, мис. криптография же микросекунддук тактык убакыт белгилери ("timestamp") үчүн.

`BigInt` түрү ыктыярдуу узундуктагы бүтүн сандарды көрсөтүү үчүн тилге жакында эле кошулган.

`BigInt` мааниси бүтүн сандын аягына `n` кошуу менен түзүлөт:

```js
// аягында "n" белгиси бул BigInt экенин билдирет
const bigInt = 1234567890123456789012345678901234567890n;
```

`BigInt` сандары сейрек талап кылынгандыктан, биз аларды бөлөк <info:bigint> бөлүмүндө караштырабыз. Ушунчалык чоң сандар керек болгондо аны окуңуз.

```smart header="Шайкештик көйгөйлөрү"
Азыркы учурда `BigInt` Firefox/Chrome/Edge/Safari браузерлеринде колдоого алынат, бирок IE'де - жок.
```

я Браузердин кайсы версиялары колдоого алынарын билүү үчүн [*MDN* BigInt шайкештик жадыбалын](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt#Browser_compatibility) карап көрсөңүз болот.

## Сап (string)

JavaScript'те сап тырмакчага алынышы керек.

```js
let str = "Салам";
let str2 = 'Жалгыз тырмакча деле болот';
let phrase = `дагы башка ${str} киргизүүгө болот`;
```

JavaScript'те тырмакчанын 3 түрү бар.

1. Кош тырмакча: `"Салам"`.
2. Жалгыз тырмакча: `'Салам'`.
3. Тескери тырмакча: <code>&#96;Салам&#96;</code>.

Кош жана жалгыз тырмакчалар "жөнөкөй" болуп саналат. JavaScript'те алардын ортосунда эч кандай айырмасы жок.

Тескери тырмакчалар кеңейтилген функцияга ээ. Алар бизге өзгөрмөлөрдү жана туюнтмаларды `${…}` ичине ороп, сапка киргизүүгө мүмкүндүк берет, мисалы:

```js run
let name = "Жакыя";

// өзгөрмөнү киргизебиз
alert( `Салам, *!*${name}*/!*!` ); // Салам, Жакыя!

// туюнтманы киргизебиз
alert( `натыйжа: *!*${1 + 2}*/!*` ); // натыйжа: 3
```

`${…}` ичиндеги туюнтма эсептелинет жана натыйжасы саптын бир бөлүгү болуп калат. Биз ал жерге каалаган нерсени киргизе алабыз: `name` сыяктуу өзгөрмөнү же `1 + 2` сыяктуу арифметикалык туюнтманы же татаалыраак нерсени.

Көнүл буруңуз, муну тескери тырмакча менен гана кылууга болот. Башка тырмакчаларда ушундай камтылуу функционалдуулугу жок!

```js run
alert( "натыйжа: ${1 + 2}" ); // натыйжа: ${1 + 2} (кош тырмакча эч нерсе кылбайт)
```

Биз <info:string> бөлүмүндө саптарды кененирээк караштырабыз.

```smart header="*Символ* (*character*) түрү жок."
Кээ бир тилдерде бир белгини белгилөө үчүн атайын "character" түрү бар. Мисалы, C жана Java тилдеринде бул `char`.

JavaScript'те мындай түр жок. Бир гана түр бар: `string`. Сап нөл белгилерден (бош болушу), бир белгиден же алардын көбүнөн турушу мүмкүн.
```

## Логикалык түр (boolean)

Логикалык түр эки маанини гана кабыл алат: `true` (чындык) жана `false` (жалган).

Бул түр көбүнчө ооба/жок маанилерин сактоо үчүн колдонулат: `true` - "ооба, туура", ал эми `false` - "жок, туура эмес" дегенди билдирет.

Мисалы үчүн:

```js
let nameFieldChecked = true; // ооба, аты текшерилди
let ageFieldChecked = false; // жок, курагы текшерилбеди
```

Ошондой эле логикалык маанилерди салыштыруулардын натыйжасында алууга болот:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (салыштыруунун натыйжасы - "ооба")
```

Биз логикалык маанилерди <info:logical-operators> бөлүмүндө тереңирээк караштырабыз.

## "null" мааниси

Атайын `null` мааниси жогоруда сыпатталган түрлөрдүн бирине да таандык эмес.

Ал `null` маанисин гана камтыган өзүнчө түрдү түзөт:

```js
let age = null;
```

JavaScript'те `null` кээ бир башка тилдердегидей "болбогон маңызга шилтеме" же "нөлдүк көрсөткүч" болуп саналбайт.

Бул жөн гана "эч нерсе", "бош" же "белгисиз маанини" билдирген өзгөчө маани.

Жогорудагы коддо `age` белгисиз экени айтылат.

## "undefined" мааниси

Атайын `undefined` мааниси да өзүнчө турат. Ал `null` сыяктуу өзүнүн түрүн түзөт.

`undefined` "маани ыйгарылган эмес" дегенди билдирет.

Эгерде өзгөрмө жарыяланып, бирок ага эч кандай маани ыйгарылбаса, анда анын мааниси `undefined` болот:

```js run
let age;

alert(age); // "undefined" көрсөтөт
```

Техникалык жактан өзгөрмөгө `undefined` ыйгарылышы мүмкүн:

```js run
let age = 100;

// маанисин undefined'ге өзгөртөбүз
age = undefined;

alert(age); // "undefined"
```

...Бирок биз муну кылууга сунуштабайбыз. Адатта, өзгөрмөгө "бош" же "белгисиз" маани ыйгаруу үчүн `null` колдонулат, ал эми `undefined` ыйгарылбаган нерселер үчүн демейки баштапкы маани катары сакталат.

## Маңыздар (object) жана символдор (symbol)

`object` -- өзгөчө түр.

All other types are called "primitive" because their values can contain only a single thing (be it a string or a number or whatever). In contrast, objects are used to store collections of data and more complex entities.

Being that important, objects deserve a special treatment. We'll deal with them later in the chapter <info:object>, after we learn more about primitives.

The `symbol` type is used to create unique identifiers for objects. We have to mention it here for the sake of completeness, but also postpone the details till we know objects.

## The typeof operator [#type-typeof]

The `typeof` operator returns the type of the argument. It's useful when we want to process values of different types differently or just want to do a quick check.

A call to `typeof x` returns a string with the type name:

```js
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

*!*
typeof Math // "object"  (1)
*/!*

*!*
typeof null // "object"  (2)
*/!*

*!*
typeof alert // "function"  (3)
*/!*
```

The last three lines may need additional explanation:

1. `Math` is a built-in object that provides mathematical operations. We will learn it in the chapter <info:number>. Here, it serves just as an example of an object.
2. The result of `typeof null` is `"object"`. That's an officially recognized error in `typeof`, coming from very early days of JavaScript and kept for compatibility. Definitely, `null` is not an object. It is a special value with a separate type of its own. The behavior of `typeof` is wrong here.
3. The result of `typeof alert` is `"function"`, because `alert` is a function. We'll study functions in the next chapters where we'll also see that there's no special "function" type in JavaScript. Functions belong to the object type. But `typeof` treats them differently, returning `"function"`. That also comes from the early days of JavaScript. Technically, such behavior isn't correct, but can be convenient in practice.

```smart header="The `typeof(x)` syntax"
You may also come across another syntax: `typeof(x)`. It's the same as `typeof x`.

To put it clear: `typeof` is an operator, not a function. The parentheses here aren't a part of `typeof`. It's the kind of parentheses used for mathematical grouping.

Usually, such parentheses contain a mathematical expression, such as `(2 + 2)`, but here they contain only one argument `(x)`. Syntactically, they allow to avoid a space between the `typeof` operator and its argument, and some people like it.

Some people prefer `typeof(x)`, although the `typeof x` syntax is much more common.
```

## Summary

There are 8 basic data types in JavaScript.

- Seven primitive data types:
    - `number` for numbers of any kind: integer or floating-point, integers are limited by <code>±(2<sup>53</sup>-1)</code>.
    - `bigint` for integer numbers of arbitrary length.
    - `string` for strings. A string may have zero or more characters, there's no separate single-character type.
    - `boolean` for `true`/`false`.
    - `null` for unknown values -- a standalone type that has a single value `null`.
    - `undefined` for unassigned values -- a standalone type that has a single value `undefined`.
    - `symbol` for unique identifiers.
- And one non-primitive data type:
    - `object` for more complex data structures.

The `typeof` operator allows us to see which type is stored in a variable.

- Usually used as `typeof x`, but `typeof(x)` is also possible.
- Returns a string with the name of the type, like `"string"`.
- For `null` returns `"object"` -- this is an error in the language, it's not actually an object.

In the next chapters, we'll concentrate on primitive values and once we're familiar with them, we'll move on to objects.
