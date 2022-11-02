# Базалык операторлор, математика

Көптөгөн операторлор бизге мектептен таанымал, булар кошуу `+`, көбөйтүү `*`, кемитүү `-` ж.б.

Бул бөлүмдө биз жөнөкөй операторлордон баштайбыз, андан кийин мектептеги арифметикада окутулбаган JavaScript спецификалык аспектилерине топтолобуз.

## Терминдер: "унардык", "бинардык", "операнд"

Улантуудан мурун, кээ бир жалпы терминологияны түшүнүп алалы.

- *An operand* -- is what operators are applied to. For instance, in the multiplication of `5 * 2` there are two operands: the left operand is `5` and the right operand is `2`. Sometimes, people call these "arguments" instead of "operands".
- An operator is *unary* if it has a single operand. For example, the unary negation `-` reverses the sign of a number:

    ```js run
    let x = 1;

    *!*
    x = -x;
    */!*
    alert( x ); // -1, унардык минус колдонулду
    ```
- An operator is *binary* if it has two operands. The same minus exists in binary form as well:

    ```js run no-beautify
    let x = 1, y = 3;
    alert( y - x ); // 2, бинардык минус маанилерди кемитет
    ```

    Formally, in the examples above we have two different operators that share the same symbol: the negation operator, a unary operator that reverses the sign, and the subtraction operator, a binary operator that subtracts one number from another.

## Математика

Төмөнкү математикалык операциялар колдоого алынат:

- Кошуу `+`,
- Кемитүү `-`,
- Көбөйтүү `*`,
- Бөлүү `/`,
- Бөлүүнүн калдыгын алуу `%`,
- Даражага көтөрүү `**`.

Алгачкы төрт оператор түшүнүктүү, бирок `%` жана `**` жөнүндө бир нече сөз айтуу керек.

### Бөлүүнүн калдыгы %

Бөлүүнүн калдыгын алуунун оператору `%`, көрүнүшүнө карабастан, пайыздар менен байланышпайт.

`a % b` натыйжасы - бул `a` менен `b`'нын бүтүн сандык бөлүүнүн [калдыгы](https://en.wikipedia.org/wiki/Remainder).

Мисалы үчүн:

```js run
alert( 5 % 2 ); // 1, 5ти 2ге бөлүүнүн калдыгы
alert( 8 % 3 ); // 2, 8ди 3кө бөлүүнүн калдыгы
```

### Даражага көтөрүү **

`a ** b` туюнтмасында даражага көтөрүү оператору `a`'ны өзүнө `b` эсеге көбөйтөт.

Мектепте биз муну a<sup>b</sup> деп жазабыз.

Мисалы үчүн:

```js run
alert( 2 ** 2 ); // 2² = 4
alert( 2 ** 3 ); // 2³ = 8
alert( 2 ** 4 ); // 2⁴ = 16
```

Математикадагыдай эле, даражага көтөрүү операторун бөлчөктүк сандар үчүн да колдонууга болот.

Мисалы, чарчы тамыр бул ½ даражага көтөрүүсү:

```js run
alert( 4 ** (1/2) ); // 2 (1/2 даражасы чарчы тамыр менен бирдей)
alert( 8 ** (1/3) ); // 2 (1/3 даражасы кубдук тамыр менен бирдей)
```


## Бинардык + менен саптарды кошуу

Келгиле, мектеп арифметикасынын алкагына кирбеген JavaScript операторлорунун өзгөчөлүктөрү менен таанышалы.

Адатта, плюс оператору `+` сандарды кошот.

Бирок, бинардык `+` саптарга колдонулса, ал аларды бириктирет:

```js
let s = "менин" + "сабым";
alert(s); // менинсабым
```

Көңүл буруңуз, эгерде операнддардын бири сап болсо, башкасы ошондой эле сапка айландырылат.

Мисалы:

```js run
alert( '1' + 2 ); // "12"
alert( 2 + '1' ); // "21"
```

Караңыз, биринчи операнд саппы же экинчисиби, айырмасы жок.

Мына татаалыраак мисал:

```js run
alert(2 + 2 + '1' ); // "41", "221" эмес
```

Here, operators work one after another. The first `+` sums two numbers, so it returns `4`, then the next `+` adds the string `1` to it, so it's like `4 + '1' = '41'`.

```js run
alert('1' + 2 + 2); // "122", "14" эмес
```
Here, the first operand is a string, the compiler treats the other two operands as strings too. The `2` gets concatenated to `'1'`, so it's like `'1' + 2 = "12"` and `"12" + 2 = "122"`.

The binary `+` is the only operator that supports strings in such a way. Other arithmetic operators work only with numbers and always convert their operands to numbers.

Мисалы, кемитүү жана бөлүү:

```js run
alert( 6 - '2' ); // 4, '2' санга айландырылат
alert( '6' / '2' ); // 3, эки операнд тең сапка айландырылат
```

## Санга келтирүү, унардык +

Плюс `+` эки формада бар: биз жогоруда колдонгон бинардык форма жана унардык форма.

The unary plus or, in other words, the plus operator `+` applied to a single value, doesn't do anything to numbers. But if the operand is not a number, the unary plus converts it into a number.

Мисалы:

```js run
// Сандарга таасир этпейт
let x = 1;
alert( +x ); // 1

let y = -2;
alert( +y ); // -2

*!*
// Сандык эмес маанилерди айландырат
alert( +true ); // 1
alert( +"" );   // 0
*/!*
```

Бул чындыгында `Number(...)` менен бирдей, бирок көрүнүшү кыскараак.

The need to convert strings to numbers arises very often. For example, if we are getting values from HTML form fields, they are usually strings. What if we want to sum them?

Бинардык плюс аларды сап катары кошот:

```js run
let apples = "2";
let oranges = "3";

alert( apples + oranges ); // "23", бинардык плюс саптарды бириктирет
```

Эгерде биз аларды сандар катары колдонууну кааласак, анда биз аларды айландырып, андан кийин суммалашыбыз керек:

```js run
let apples = "2";
let oranges = "3";

*!*
// both values converted to numbers before the binary plus
alert( +apples + +oranges ); // 5
*/!*

// узунураак вариант
// alert( Number(apples) + Number(oranges) ); // 5
```

From a mathematician's standpoint, the abundance of pluses may seem strange. But from a programmer's standpoint, there's nothing special: unary pluses are applied first, they convert strings to numbers, and then the binary plus sums them up.

Why are unary pluses applied to values before the binary ones? As we're going to see, that's because of their *higher precedence*.

## Операторлордун приоритети

If an expression has more than one operator, the execution order is defined by their *precedence*, or, in other words, the default priority order of operators.

From school, we all know that the multiplication in the expression `1 + 2 * 2` should be calculated before the addition. That's exactly the precedence thing. The multiplication is said to have *a higher precedence* than the addition.

Parentheses override any precedence, so if we're not satisfied with the default order, we can use them to change it. For example, write `(1 + 2) * 2`.

There are many operators in JavaScript. Every operator has a corresponding precedence number. The one with the larger number executes first. If the precedence is the same, the execution order is from left to right.

Here's an extract from the [precedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) (you don't need to remember this, but note that unary operators are higher than corresponding binary ones):

| Приоритет | Аталыш | Белги |
|------------|------|------|
| ... | ... | ... |
| 14 | унардык плюс | `+` |
| 14 | унардык минус | `-` |
| 13 | даражага көтөрүү | `**` |
| 12 | көбөйтүү | `*` |
| 12 | бөлүү | `/` |
| 11 | кошуу | `+` |
| 11 | кемитүү | `-` |
| ... | ... | ... |
| 2 | ыйрагуу | `=` |
| ... | ... | ... |

As we can see, the "unary plus" has a priority of `14` which is higher than the `11` of "addition" (binary plus). That's why, in the expression `"+apples + +oranges"`, unary pluses work before the addition.

## Ыйгаруу

Let's note that an assignment `=` is also an operator. It is listed in the precedence table with the very low priority of `2`.

That's why, when we assign a variable, like `x = 2 * 2 + 1`, the calculations are done first and then the `=` is evaluated, storing the result in `x`.

```js
let x = 2 * 2 + 1;

alert( x ); // 5
```

### Ыйгаруу = маанини кайтарат

The fact of `=` being an operator, not a "magical" language construct has an interesting implication.

All operators in JavaScript return a value. That's obvious for `+` and `-`, but also true for `=`.

The call `x = value` writes the `value` into `x` *and then returns it*.

Here's a demo that uses an assignment as part of a more complex expression:

```js run
let a = 1;
let b = 2;

*!*
let c = 3 - (a = b + 1);
*/!*

alert( a ); // 3
alert( c ); // 0
```

In the example above, the result of expression `(a = b + 1)` is the value which was assigned to `a` (that is `3`). It is then used for further evaluations.

Funny code, isn't it? We should understand how it works, because sometimes we see it in JavaScript libraries.

Although, please don't write the code like that. Such tricks definitely don't make code clearer or readable.

### Чынжырча ыйгаруу

Another interesting feature is the ability to chain assignments:

```js run
let a, b, c;

*!*
a = b = c = 2 + 2;
*/!*

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

Chained assignments evaluate from right to left. First, the rightmost expression `2 + 2` is evaluated and then assigned to the variables on the left: `c`, `b` and `a`. At the end, all the variables share a single value.

Once again, for the purposes of readability it's better to split such code into few lines:

```js
c = 2 + 2;
b = c;
a = c;
```
That's easier to read, especially when eye-scanning the code fast.

## Modify-in-place

We often need to apply an operator to a variable and store the new result in that same variable.

Мисалы:

```js
let n = 2;
n = n + 5;
n = n * 2;
```

This notation can be shortened using the operators `+=` and `*=`:

```js run
let n = 2;
n += 5; // now n = 7 (same as n = n + 5)
n *= 2; // now n = 14 (same as n = n * 2)

alert( n ); // 14
```

Short "modify-and-assign" operators exist for all arithmetical and bitwise operators: `/=`, `-=`, etc.

Such operators have the same precedence as a normal assignment, so they run after most other calculations:

```js run
let n = 2;

n *= 3 + 5; // right part evaluated first, same as n *= 8

alert( n ); // 16  
```

## Инкремент/декремент

<!-- Can't use -- in title, because the built-in parser turns it into a 'long dash' – -->

Increasing or decreasing a number by one is among the most common numerical operations.

Ал үчүн атайын операторлор бар:

- **Инкремент** `++` өзгөрмөнү 1ге көбөйтөт:

    ```js run no-beautify
    let counter = 2;
    counter++;        // counter = counter + 1 сыяктуу иштейт, бирок жазуусу кыскараак
    alert( counter ); // 3
    ```
- **Декремент** `--` өзгөрмөнү 1ге азайтат:

    ```js run no-beautify
    let counter = 2;
    counter--;        // counter = counter - 1 сыяктуу иштейт, бирок жазуусу кыскараак
    alert( counter ); // 1
    ```

```warn
Increment/decrement can only be applied to variables. Trying to use it on a value like `5++` will give an error.
```

The operators `++` and `--` can be placed either before or after a variable.

- When the operator goes after the variable, it is in "postfix form": `counter++`.
- The "prefix form" is when the operator goes before the variable: `++counter`.

Both of these statements do the same thing: increase `counter` by `1`.

Is there any difference? Yes, but we can only see it if we use the returned value of `++/--`.

Let's clarify. As we know, all operators return a value. Increment/decrement is no exception. The prefix form returns the new value while the postfix form returns the old value (prior to increment/decrement).

Айырмачылыгын көрүү үчүн, мына мисал:

```js run
let counter = 1;
let a = ++counter; // (*)

alert(a); // *!*2*/!*
```

In the line `(*)`, the *prefix* form `++counter` increments `counter` and returns the new value, `2`. So, the `alert` shows `2`.

Эми постфикс формасын колдонолу:

```js run
let counter = 1;
let a = counter++; // (*) ++counter counter++'ка алмашты

alert(a); // *!*1*/!*
```

In the line `(*)`, the *postfix* form `counter++` also increments `counter` but returns the *old* value (prior to increment). So, the `alert` shows `1`.

Жыйынтыктайлы:

- If the result of increment/decrement is not used, there is no difference in which form to use:

    ```js run
    let counter = 0;
    counter++;
    ++counter;
    alert( counter ); // 2, the lines above did the same
    ```
- If we'd like to increase a value *and* immediately use the result of the operator, we need the prefix form:

    ```js run
    let counter = 0;
    alert( ++counter ); // 1
    ```
- If we'd like to increment a value but use its previous value, we need the postfix form:

    ```js run
    let counter = 0;
    alert( counter++ ); // 0
    ```

````smart header="Increment/decrement among other operators"
The operators `++/--` can be used inside expressions as well. Their precedence is higher than most other arithmetical operations.

For instance:

```js run
let counter = 1;
alert( 2 * ++counter ); // 4
```

Compare with:

```js run
let counter = 1;
alert( 2 * counter++ ); // 2, because counter++ returns the "old" value
```

Though technically okay, such notation usually makes code less readable. One line does multiple things -- not good.

While reading code, a fast "vertical" eye-scan can easily miss something like `counter++` and it won't be obvious that the variable increased.

We advise a style of "one line -- one action":

```js run
let counter = 1;
alert( 2 * counter );
counter++;
```
````

## Bitwise operators

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.

These operators are not JavaScript-specific. They are supported in most programming languages.

The list of operators:

- AND ( `&` )
- OR ( `|` )
- XOR ( `^` )
- NOT ( `~` )
- LEFT SHIFT ( `<<` )
- RIGHT SHIFT ( `>>` )
- ZERO-FILL RIGHT SHIFT ( `>>>` )

These operators are used very rarely, when we need to fiddle with numbers on the very lowest (bitwise) level. We won't need these operators any time soon, as web development has little use of them, but in some special areas, such as cryptography, they are useful. You can read the [Bitwise Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#bitwise_operators) chapter on MDN when a need arises.

## Comma

The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it's used to write shorter code, so we need to know it in order to understand what's going on.

The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.

For example:

```js run
*!*
let a = (1 + 2, 3 + 4);
*/!*

alert( a ); // 7 (the result of 3 + 4)
```

Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.

```smart header="Comma has a very low precedence"
Please note that the comma operator has very low precedence, lower than `=`, so parentheses are important in the example above.

Without them: `a = 1 + 2, 3 + 4` evaluates `+` first, summing the numbers into `a = 3, 7`, then the assignment operator `=` assigns `a = 3`, and the rest is ignored. It's like `(a = 1 + 2), 3 + 4`.
```

Why do we need an operator that throws away everything except the last expression?

Sometimes, people use it in more complex constructs to put several actions in one line.

For example:

```js
// three operations in one line
for (*!*a = 1, b = 3, c = a * b*/!*; a < 10; a++) {
 ...
}
```

Such tricks are used in many JavaScript frameworks. That's why we're mentioning them. But usually they don't improve code readability so we should think well before using them.
