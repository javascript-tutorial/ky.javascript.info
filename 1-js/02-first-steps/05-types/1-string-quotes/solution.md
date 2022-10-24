Тескери тырмакчалар `${...}` ичиндеги туюнтманы сапка киргизүүгө мүмкүндүк берет.

```js run
let name = "Ilya";

// туюнтма - 1 саны
alert( `hello ${1}` ); // hello 1

// туюнтма - "name" сабы
alert( `hello ${"name"}` ); // hello name

// туюнтма - өзгөрмө, аны сапка киргизебиз
alert( `hello ${name}` ); // hello Ilya
```
