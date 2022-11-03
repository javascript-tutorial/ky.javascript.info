# Түрлөрдү айландыруу

Көпчүлүк учурда операторлор жана функциялар аларга берилген маанилерди автоматтык түрдө керектүү түргө айландырышат.

Мисалы, `alert` каалаган маанини автоматтык түрдө сапка айландырат. Математикалык операторлор маанилерди сандарга айландырат.

Ошондой эле биз маанини күтүлгөн түргө айкын айландырышыбыз керек болгон учурлар бар.

```smart header="Not talking about objects yet"
Бул бөлүмдө биз маңыздарга тийишпейбиз. Азырынча жөн гана примитивдер жөнүндө сүйлөшөбүз.

Кийинчерээк, маңыздар менен таанышкандан кийин, алардын айландыруусун <info:object-toprimitive> бөлүмүндө карайбыз.
```

## Сапка айландыруу

Сапка айландыруу бизге маанинин сап формасы керек болгондо болот.

Мисалы, `alert(value)` муну маанисин көрсөтүү үчүн кылат.

Ошондой эле биз маанини сапка айландыруу үчүн `String(value)` функциясын чакыра алабыз:

```js run
let value = true;
alert(typeof value); // boolean

*!*
value = String(value); // эми value - бул "true" сабы
alert(typeof value); // string
*/!*
```

Саптарды айландыруу анык түрдө болот. `false` - `"false"` болуп калат, `null` - `"null"` болуп калат ж.б.у.с.

## Санга айландыруу

Numeric conversion happens in mathematical functions and expressions automatically.

For example, when division `/` is applied to non-numbers:

```js run
alert( "6" / "2" ); // 3, саптар сандарга айланды
```

We can use the `Number(value)` function to explicitly convert a `value` to a number:

```js run
let str = "123";
alert(typeof str); // string

let num = Number(str); // 123 санына айланат

alert(typeof num); // number
```

Explicit conversion is usually required when we read a value from a string-based source like a text form but expect a number to be entered.

If the string is not a valid number, the result of such a conversion is `NaN`. For instance:

```js run
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, conversion failed
```

Numeric conversion rules:

| Маани |  Натыйжа |
|-------|-------------|
|`undefined`|`NaN`|
|`null`|`0`|
|<code>true&nbsp;and&nbsp;false</code> | `1` and `0` |
| `string` | Whitespaces (includes spaces, tabs `\t`, newlines `\n` etc.) from the start and end are removed. If the remaining string is empty, the result is `0`. Otherwise, the number is "read" from the string. An error gives `NaN`. |

Мисалдар:

```js run
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN ("z" белгинин ордунда санды окуу катасы)
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

Please note that `null` and `undefined` behave differently here: `null` becomes zero while `undefined` becomes `NaN`.

Most mathematical operators also perform such conversion, we'll see that in the next chapter.

## Логикалык түргө айландыруу

Логикалык айландыруу эң жөнөкөй.

It happens in logical operations (later we'll meet condition tests and other similar things) but can also be performed explicitly with a call to `Boolean(value)`.

Айландырууну эрежелери:

- Values that are intuitively "empty", like `0`, an empty string, `null`, `undefined`, and `NaN`, become `false`.
- Башка маанилер `true` болуп калат.

Мисалы үчүн:

```js run
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("салам") ); // true
alert( Boolean("") ); // false
```

````warn header="Please note: the string with zero `\"0\"` is `true`"
Some languages (namely PHP) treat `"0"` as `false`. But in JavaScript, a non-empty string is always `true`.

```js run
alert( Boolean("0") ); // true
alert( Boolean(" ") ); // spaces, also true (any non-empty string is true)
```
````

## Корутунду

The three most widely used type conversions are to string, to number, and to boolean.

**`String Conversion`** -- Occurs when we output something. Can be performed with `String(value)`. The conversion to string is usually obvious for primitive values.

**`Numeric Conversion`** -- Occurs in math operations. Can be performed with `Number(value)`.

The conversion follows the rules:

| Маани |  Натыйжа |
|-------|-------------|
|`undefined`|`NaN`|
|`null`|`0`|
|<code>true&nbsp;/&nbsp;false</code> | `1 / 0` |
| `string` | The string is read "as is", whitespaces (includes spaces, tabs `\t`, newlines `\n` etc.) from both sides are ignored. An empty string becomes `0`. An error gives `NaN`. |

**`Boolean Conversion`** -- Occurs in logical operations. Can be performed with `Boolean(value)`.

Follows the rules:

| Маани |  Натыйжа |
|-------|-------------|
|`0`, `null`, `undefined`, `NaN`, `""` |`false`|
|any other value| `true` |


Most of these rules are easy to understand and memorize. The notable exceptions where people usually make mistakes are:

- `undefined` is `NaN` as a number, not `0`.
- `"0"` and space-only strings like `"   "` are true as a boolean.

Objects aren't covered here. We'll return to them later in the chapter <info:object-toprimitive> that is devoted exclusively to objects after we learn more basic things about JavaScript.
