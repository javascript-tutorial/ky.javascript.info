# Шарттык бутактануу: if, '?'

Sometimes, we need to perform different actions based on different conditions.

To do that, we can use the `if` statement and the conditional operator `?`, that's also called a "question mark" operator.

## "if" нускамасы

The `if(...)` statement evaluates a condition in parentheses and, if the result is `true`, executes a block of code.

Мисалы:

```js run
let year = prompt('ECMAScript-2015 спецификациясы канчанчы жылы жарыяланган??', '');

*!*
if (year == 2015) alert( 'Туура айтасыз!' );
*/!*
```

In the example above, the condition is a simple equality check (`year == 2015`), but it can be much more complex.

If we want to execute more than one statement, we have to wrap our code block inside curly braces:

```js
if (year == 2015) {
  alert( "Туура!" );
  alert( "Сиз абдан акылдуусуз!" );
}
```

We recommend wrapping your code block with curly braces `{}` every time you use an `if` statement, even if there is only one statement to execute. Doing so improves readability.

## Логикалык айландыруу

The `if (…)` statement evaluates the expression in its parentheses and converts the result to a boolean.

Let's recall the conversion rules from the chapter <info:type-conversions>:

- A number `0`, an empty string `""`, `null`, `undefined`, and `NaN` all become `false`. Because of that they are called "falsy" values.
- Other values become `true`, so they are called "truthy".

Ошондо, мындай шарттан кийин кеткен код эч качан аткарылбайт:

```js
if (0) { // 0 бул жалган
  ...
}
```

...жана мындай шарттан кийин ал ар дайым аткарылат:

```js
if (1) { // 1 бул чындык
  ...
}
```

Биз ошондой эле алдын ала айландырылган логикалык маанини `if`ге өткөрө алабыз, мисалы:

```js
let cond = (year == 2015); // теңештирүү true же false'го айланат

if (cond) {
  ...
}
```

## "else" пункту

<<<<<<< HEAD
`if` нускамасы кошумча "else" блогун камтышы мүмкүн. Шарт жалган болгондо ал аткарылат.
=======
The `if` statement may contain an optional `else` block. It executes when the condition is falsy.
>>>>>>> 34a80e70f8cce5794be259d25f815d7a7db7cbe3

Мисалы:
```js run
let year = prompt('ECMAScript-2015 спецификациясы канчанчы жылы жарыяланган?', '');

if (year == 2015) {
  alert( 'Туура таптыңыз!' );
} else {
    alert( 'Кантип ушунчалык ката кетиресиз?' ); // 2015-тен башкасы
}
```

## Бир нече шарт түзүү: "else if"

Кээде биз шарттын бир нече варианттарын сынагыбыз келет. `else if` пункту бизге муну кылууга жол берет.

Мисалы:

```js run
let year = prompt('ECMAScript-2015 спецификациясы канчанчы жылы жарыяланган?', '');

if (year < 2015) {
  alert( 'Өтө эрте...' );
} else if (year > 2015) {
  alert( 'Өтө кеч' );
} else {
  alert( 'Дал ошондой!' );
}
```

In the code above, JavaScript first checks `year < 2015`. If that is falsy, it goes to the next condition `year > 2015`. If that is also falsy, it shows the last `alert`.

`else if` блоктору көбүрөөк болушу мүмкүн. Эң акыркы `else` кошумча болуп саналат.

## Шарттык оператор '?'

Кээде биз шартка көз каранды болгон өзгөрмө ыйгарышыбыз керек.

Мисалы үчүн:

```js run no-beautify
let accessAllowed;
let age = prompt('Сиз канча жаштасыз?', '');

*!*
if (age > 18) {
  accessAllowed = true;
} else {
  accessAllowed = false;
}
*/!*

alert(accessAllowed);
```

"Шарттык" же "суроо белгиси" деп аталган оператор жогорудагы шартты кыскараак жана жөнөкөй жол менен жасоого жол берет.

The operator is represented by a question mark `?`. Sometimes it's called "ternary", because the operator has three operands. It is actually the one and only operator in JavaScript which has that many.

Анын жазылышы:
```js
let result = condition ? value1 : value2;
```

`condition` мындай эсептелинет: эгерде ал чындык болсо `value1` кайтарылат, болбосо -- `value2`.

Мисалы:

```js
let accessAllowed = (age > 18) ? true : false;
```

Technically, we can omit the parentheses around `age > 18`. The question mark operator has a low precedence, so it executes after the comparison `>`.

This example will do the same thing as the previous one:

```js
// the comparison operator "age > 18" executes first anyway
// (no need to wrap it into parentheses)
let accessAllowed = age > 18 ? true : false;
```

But parentheses make the code more readable, so we recommend using them.

````smart
In the example above, you can avoid using the question mark operator because the comparison itself returns `true/false`:

```js
// the same
let accessAllowed = age > 18;
```
````

## Бир нече '?'

Суроо белгиси операторлорунун `?` ырааттуулугу бирден ашык шартка көз каранды болгон маанини кайтара алат.

Мисалы үчүн:
```js run
let age = prompt('жашыңыз?', 18);

let message = (age < 3) ? 'Салам, балакай!' :
  (age < 18) ? 'Салам!' :
  (age < 100) ? 'Саламатсызбы!' :
  'Жашыңыз кандай укмуштуу!';

alert( message );
```

It may be difficult at first to grasp what's going on. But after a closer look, we can see that it's just an ordinary sequence of tests:

1. The first question mark checks whether `age < 3`.
2. If true -- it returns `'Hi, baby!'`. Otherwise, it continues to the expression after the colon ":", checking `age < 18`.
3. If that's true -- it returns `'Hello!'`. Otherwise, it continues to the expression after the next colon ":", checking `age < 100`.
4. If that's true -- it returns `'Greetings!'`. Otherwise, it continues to the expression after the last colon ":", returning `'What an unusual age!'`.

Here's how this looks using `if..else`:
Мында `if..else` колдонгондон кийинки көрүнүшү:

```js
if (age < 3) {
  message = 'Салам, балакай!';
} else if (age < 18) {
  message = 'Салам!';
} else if (age < 100) {
  message = 'Саламатсызбы!';
} else {
  message = 'Жашыңыз кандай укмуштуу!';
}
```

## '?' белгисинин адатсыз колдонушу

Кээде суроо белгиси `?` - `if`'ти алмаштыруучу катары колдонулат:

```js run no-beautify
let company = prompt('Кайсы компания JavaScript'ти түзгөн?', '');

*!*
(company == 'Netscape') ?
   alert('Туура!') : alert('Туура эмес.');
*/!*
```

`company == 'Netscape'` шартына жараша, `?` белгисинен кийинки биринчи же экинчи туюнтма аткарылып, билдирүү көрсөтүлөт.

Бул жерде натыйжаны өзгөрмөгө ыйгарбайбыз. Анын ордуна, шартка жараша ар кандай кодду аткарабыз.

**Суроо белгиси операторун мындай колдонгону сунушталбайт.**

The notation is shorter than the equivalent `if` statement, which appeals to some programmers. But it is less readable.

Here is the same code using `if` for comparison:

```js run no-beautify
let company = prompt('Кайсы компания JavaScript'ти түзгөн?', '');

*!*
if (company == 'Netscape') {
  alert('Туура!');
} else {
  alert('Туура эмес.');
}
*/!*
```

Биздин көзүбүз кодду өйдөдөн ылдый көрөт. Узун, горизонталдуу нускамаларга караганда бир нече саптардан турган код блокторун түшүнүүгө оңоюраак.

Суроо белгиси операторунун `?` максаты – анын шартына жараша тигил же бул маанини кайтаруу. Сураныч, аны дал ушул үчүн колдонуңуз. Коддун ар кандай бутактарын аткарыш керек болгондо `if` колдонуңуз.
