Жообу: `1`, андан кийин `undefined`.

```js run
alert( alert(1) && alert(2) );
```

`alert` чакыруусу `undefined`'ди кайтарат (ал жөн гана билдирүүнү көрсөтөт, андыктан маанилүү кайтаруу болбойт).

Мунун себеби, `&&` сол операндды аткарат (`1` чыгарылат), жана дароо токтойт, анткени `undefined` жалган маани. Ал эми `&&` жалган маанини издейт жана аны кайтарат.
