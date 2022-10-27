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

JavaScript'те "number" түрү <code>(2<sup>53</sup>-1)</code>ден чоңураак (бул `9007199254740991`) же <code>-(2<sup>53</sup>-1)</code>ден кичине бүтүн сандык маанилерди билдире албайт. Бул алардын ички ишке ашыруусунан улам келип чыккан техникалык чектөөсү.

To be really precise, the "number" type can store larger integers (up to <code>1.7976931348623157 * 10<sup>308</sup></code>), but outside of the safe integer range <code>±(2<sup>53</sup>-1)</code> there'll be a precision error, because not all digits fit into the fixed 64-bit storage. So an "approximate" value may be stored.

For example, these two numbers (right above the safe range) are the same:

```js
console.log(9007199254740991 + 1); // 9007199254740992
console.log(9007199254740991 + 2); // 9007199254740992
```

So to say, all odd integers greater than <code>(2<sup>53</sup>-1)</code> can't be stored at all in the "number" type.

For most purposes <code>±(2<sup>53</sup>-1)</code> range is quite enough, but sometimes we need the entire range of really big integers, e.g. for cryptography or microsecond-precision timestamps.

`BigInt` type was recently added to the language to represent integers of arbitrary length.

A `BigInt` value is created by appending `n` to the end of an integer:

```js
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

As `BigInt` numbers are rarely needed, we don't cover them here, but devoted them a separate chapter <info:bigint>. Read it when you need such big numbers.


```smart header="Compatibility issues"
Right now, `BigInt` is supported in Firefox/Chrome/Edge/Safari, but not in IE.
```

You can check [*MDN* BigInt compatibility table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt#Browser_compatibility) to know which versions of a browser are supported.

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

Double and single quotes are "simple" quotes. There's practically no difference between them in JavaScript.

Backticks are "extended functionality" quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`, for example:

```js run
let name = "Жакыя";

// өзгөрмөнү киргизебиз
alert( `Салам, *!*${name}*/!*!` ); // Салам, Жакыя!

// туюнтманы киргизебиз
alert( `натыйжа: *!*${1 + 2}*/!*` ); // натыйжа: 3
```

The expression inside `${…}` is evaluated and the result becomes a part of the string. We can put anything in there: a variable like `name` or an arithmetical expression like `1 + 2` or something more complex.

Please note that this can only be done in backticks. Other quotes don't have this embedding functionality!
```js run
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double quotes do nothing)
```

We'll cover strings more thoroughly in the chapter <info:string>.

```smart header="There is no *character* type."
In some languages, there is a special "character" type for a single character. For example, in the C language and in Java it is called "char".

In JavaScript, there is no such type. There's only one type: `string`. A string may consist of zero characters (be empty), one character or many of them.
```

## Логикалык түр (boolean)

The boolean type has only two values: `true` and `false`.

This type is commonly used to store yes/no values: `true` means "yes, correct", and `false` means "no, incorrect".

For instance:

```js
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

Boolean values also come as a result of comparisons:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
```

We'll cover booleans more deeply in the chapter <info:logical-operators>.

## "null" мааниси

The special `null` value does not belong to any of the types described above.

It forms a separate type of its own which contains only the `null` value:

```js
let age = null;
```

In JavaScript, `null` is not a "reference to a non-existing object" or a "null pointer" like in some other languages.

It's just a special value which represents "nothing", "empty" or "value unknown".

The code above states that `age` is unknown.

## "undefined" мааниси

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.

The meaning of `undefined` is "value is not assigned".

If a variable is declared, but not assigned, then its value is `undefined`:

```js run
let age;

alert(age); // shows "undefined"
```

Technically, it is possible to explicitly assign `undefined` to a variable:

```js run
let age = 100;

// change the value to undefined
age = undefined;

alert(age); // "undefined"
```

...But we don't recommend doing that. Normally, one uses `null` to assign an "empty" or "unknown" value to a variable, while `undefined` is reserved as a default initial value for unassigned things.

## Objects and Symbols

The `object` type is special.

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
