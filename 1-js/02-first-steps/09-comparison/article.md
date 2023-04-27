# Салыштыруу операторлору

Көптөгөн салыштыруу операторлору бизге математикадан белгилүү.

JavaScript'те алар мындай жазылат:

- Чоң/кичине: <code>a &gt; b</code>, <code>a &lt; b</code>.
- Чоң/кичине же барабар: <code>a &gt;= b</code>, <code>a &lt;= b</code>.
- Барабар: `a == b`. Көңүл буруңуз, кош барабардык белгиси `==` салыштыруу үчүн колдонулат, ал эми жалгыз барабардык белгиси `a = b` ыйгарууну билдирчү.
- Барабар эмес: Математикада <code>&ne;</code> белгиси менен белгиленет, бирок JavaScript'те <code>a != b</code> деп жазылат.

Бул бөлүмдө биз салыштыруунун ар кандай түрлөрү, JavaScript аларды кантип аткарышы жана маанилүү өзгөчөлүктөрү жөнүндө көбүрөөк үйрөнөбүз.

Аягында, сиз JavaScript'теги салыштыруу "тентектиктеринен" сактануу үчүн жакшы кеңештерди таба аласыз.

## Салыштыруунун натыйжасы логикалык түргө ээ

Бардык салыштыруу операторлору логикалык түрдөгү маанини кайтарат:

- `true` -- "ооба", "туура" же "чындыкты" билдирет.
- `false` -- "жок", "туура эмес" же "жалганды" билдирет.

Мисалы:

```js run
alert( 2 > 1 );  // true (туура)
alert( 2 == 1 ); // false (туура эмес)
alert( 2 != 1 ); // true (туура)
```

Салыштыруунун натыйжасы ар кандай маани сыяктуу эле өзгөрмөгө ыйгарылышы мүмкүн:

```js run
let result = 5 > 4; // салыштыруунун натыйжасы result өзгөрмөсүнө ыйгарылат
alert( result ); // true
```

## Саптарды салыштыруу

Бир сап экинчисинен чоңураак экенин аныктоо үчүн JavaScript "алиппелик" же "лексикографиялык" деп аталган тартипти колдонот.

Башкача айтканда, саптар белгиден белгиге салыштырылат.

Мисалы:

```js run
alert( 'Я' > 'А' ); // туура (true)
alert( 'Кант' > 'Калп' ); // туура (true)
alert( 'Балдар' > 'Бал' ); // туура (true)
```

Эки сапты салыштыруу алгоритми абдан жөнөкөй:

1. Эки саптын биринчи белгилери салыштырылат.
2. Эгерде биринчи саптын биринчи белгиси башка саптардан чоң (же кичине) болсо, биринчи сап экинчисинен чоң (же кичине) болот. Салыштыруу аяктады.
3. Болбосо, эки саптын тең биринчи белгилери бирдей болсо, экинчи белгилери ошондой жол менен эле салыштырылат.
4. Салыштыруу саптардын бири бүтмөйүнчө уланат.
5. Эгерде эки сап бирдей узундукта аяктаса, анда алар барабар болот. Болбосо, узун сап чоңураак болуп саналат.

Жогорудагы биринчи мисалда `'Я' > 'А'` салыштыруусу биринчи кадамда аяктайт.

Экинчи `'Кант'` жана `'Калп'` сөздөрүнүн салыштыруусу белгиден белгиге салыштырылат:

1. `К` менен `К` барабар.
2. `а` менен `а` барабар.
3. `н` `л`ден чоңураак. Бул жерде салыштыруу бүтөт. Биринчи сап чоңураак.

```smart header="Чыныгы алиппе эмес, Unicode коддоосу колдонулат"
Жогоруда келтирилген салыштыруу алгоритми болжол менен сөздүктөрдө же телефон китептеринде колдонулган алгоритмге барабар, бирок так окшош эмес.

Мисалы, JavaScript'те белги регистри мааниге ээ. Баш `"A"` тамгасы кичине `"a"` тамгасына барабар эмес. Кайсынысы чоңураак? Бул кичине `"a"` тамгасы. Эмнеге? Анткени кичине тамгалар JavaScript (Unicode) колдонгон ички коддоо жадыбалында чоңураак кодго ээ. Бул коддоонун өзгөчөлүктөрүн жана натыйжаларын <info:string> бөлүмүндө карап чыгабыз.
```

## Ар кандай түрлөрдү салыштыруу

Ар кандай түрдөгү маанилер салыштырылганда, JavaScript ошол маанилерди сандарга айландырат.

Мисалы:

```js run
alert( '2' > 1 ); // true, '2' сабы 2 санына айланат
alert( '01' == 1 ); // true, '01' сабы 1 санына айланат
```

Логикалык `true` мааниси `1` болуп калат жана `false` мааниси `0` болуп калат.

Мисалы:

```js run
alert( true == 1 ); // true
alert( false == 0 ); // true
```

````smart header="Кызык натыйжа"
Төмөнкү кырдаал болушу мүмкүн:

- Эки маани барабар.
- Алардын бири логикалык `true` мааниси, экинчиси - `false`.

Мисалы:

```js run
let a = 0;
alert( Boolean(a) ); // false

let b = "0";
alert( Boolean(b) ); // true

alert(a == b); // true!
```

From JavaScript's standpoint, this result is quite normal. An equality check converts values using the numeric conversion (hence `"0"` becomes `0`), while the explicit `Boolean` conversion uses another set of rules.
````

## Катуу салыштыруу

Кадимки салыштыруу `==` операторунун көйгөйү бар. Ал `0` менен `false` маанилерин айырмалай албайт:

```js run
alert( 0 == false ); // true
```

Ошол эле көйгөй бош сап менен келип чыгат:

```js run
alert( '' == false ); // true
```

This happens because operands of different types are converted to numbers by the equality operator `==`. An empty string, just like `false`, becomes a zero.

What to do if we'd like to differentiate `0` from `false`?

**A strict equality operator `===` checks the equality without type conversion.**

In other words, if `a` and `b` are of different types, then `a === b` immediately returns `false` without an attempt to convert them.

Let's try it:

```js run
alert( 0 === false ); // false, because the types are different
```

There is also a "strict non-equality" operator `!==` analogous to `!=`.

The strict equality operator is a bit longer to write, but makes it obvious what's going on and leaves less room for errors.

## Comparison with null and undefined

There's a non-intuitive behavior when `null` or `undefined` are compared to other values.

For a strict equality check `===`
: These values are different, because each of them is a different type.

    ```js run
    alert( null === undefined ); // false
    ```

For a non-strict check `==`
: There's a special rule. These two are a "sweet couple": they equal each other (in the sense of `==`), but not any other value.

    ```js run
    alert( null == undefined ); // true
    ```

For maths and other comparisons `< > <= >=`
: `null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

Now let's see some funny things that happen when we apply these rules. And, what's more important, how to not fall into a trap with them.

### Strange result: null vs 0

Let's compare `null` with a zero:

```js run
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) *!*true*/!*
```

Mathematically, that's strange. The last result states that "`null` is greater than or equal to zero", so in one of the comparisons above it must be `true`, but they are both false.

The reason is that an equality check `==` and comparisons `> < >= <=` work differently. Comparisons convert `null` to a number, treating it as `0`. That's why (3) `null >= 0` is true and (1) `null > 0` is false.

On the other hand, the equality check `==` for `undefined` and `null` is defined such that, without any conversions, they equal each other and don't equal anything else. That's why (2) `null == 0` is false.

### An incomparable undefined

The value `undefined` shouldn't be compared to other values:

```js run
alert( undefined > 0 ); // false (1)
alert( undefined < 0 ); // false (2)
alert( undefined == 0 ); // false (3)
```

Why does it dislike zero so much? Always false!

We get these results because:

- Comparisons `(1)` and `(2)` return `false` because `undefined` gets converted to `NaN` and `NaN` is a special numeric value which returns `false` for all comparisons.
- The equality check `(3)` returns `false` because `undefined` only equals `null`, `undefined`, and no other value.

### Avoid problems

Why did we go over these examples? Should we remember these peculiarities all the time? Well, not really. Actually, these tricky things will gradually become familiar over time, but there's a solid way to avoid problems with them:

- Treat any comparison with `undefined/null` except the strict equality `===` with exceptional care.
- Don't use comparisons `>= > < <=` with a variable which may be `null/undefined`, unless you're really sure of what you're doing. If a variable can have these values, check for them separately.

## Корутунду

- Салыштыруу операторлору логикалык маанини кайтарат.
- Strings are compared letter-by-letter in the "dictionary" order.
- When values of different types are compared, they get converted to numbers (with the exclusion of a strict equality check).
- The values `null` and `undefined` equal `==` each other and do not equal any other value.
- Be careful when using comparisons like `>` or `<` with variables that can occasionally be `null/undefined`. Checking for `null/undefined` separately is a good idea.
