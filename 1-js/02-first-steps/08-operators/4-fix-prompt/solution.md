Себеби, сурам терезеси колдонуучунун киргизүүсүн сап катары кайтарат.

Демек, өзгөрмөлөр тиешелүүлүгүнө жараша `"1"` жана `"2"` маанилерин алышат.

```js run
let a = "1"; // prompt("Биринчи сан?", 1);
let b = "2"; // prompt("Экинчи сан?", 2);

alert(a + b); // 12
```

Биз `+` операторун колдонуудан мурун саптарды сандарга айландырышыбыз керек. Мисалы, `Number()` же алардын алдына `+` коюу менен.

Плюсту `+` түздөн-түз `prompt`'тун алдына коюуга болот:

```js run
let a = +prompt("Биринчи сан?", 1);
let b = +prompt("Экинчи сан?", 2);

alert(a + b); // 3
```

Же `alert`'тин ичине:

```js run
let a = prompt("Биринчи сан?", 1);
let b = prompt("Экинчи сан?", 2);

alert(+a + +b); // 3
```

Акыркы вариантта унардык жана бинардык `+` чогуу колдонулат. Укмуштай көрүнөт, туурабы?
