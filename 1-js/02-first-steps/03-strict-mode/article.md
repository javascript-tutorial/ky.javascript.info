# Катуу режими, "use strict"

Узак убакыт бою, JavaScript шайкештик көйгөйлөрү жок өнүккөн. Тилге жаңы функциялар кошулуп турган, ал эми эски функционалдуулук өзгөргөн эмес.

Бул ыкманын артыкчылыгы - болгон код иштей берген. Ал эми терс жагы - JavaScript жаратуучуларынан кабыл алынган ар кандай ката же кемчиликтүү чечим тилде түбөлүккө тыгылып калган.

Бул ECMAScript 5 (ES5) пайда болгондо 2009-жылга чейин болгон. Ал тилге жаңы функцияларды кошуп, айрымдарын өзгөрттү. Эски коддун иштеши үчүн, мындай өзгөртүүлөрдүн көбү демейки боюнча өчүрүлгөн. Андыктан биз аларды атайын `"use strict"` нускоонун жардамы менен иштетишибиз керек.

## "use strict"

Нускоо сапка окшойт: `"use strict"` же `'use strict'`. Ал скрипттин башында жайгашканда, бүтүн скрипт "заманбап" жол менен иштейт.

Мисалы:

```js
"use strict";

// бул код заманбап режиминде иштейт  
...
```

Quite soon we're going to learn functions (a way to group commands), so let's note in advance that `"use strict"` can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script.

````warn header="Ensure that \"use strict\" is at the top"
Please make sure that `"use strict"` is at the top of your scripts, otherwise strict mode may not be enabled.

Strict mode isn't enabled here:

```js no-strict
alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
```

Only comments may appear above `"use strict"`.
````

```warn header="There's no way to cancel `use strict`"
There is no directive like `"no use strict"` that reverts the engine to old behavior.

Once we enter strict mode, there's no going back.
```

## Browser console

When you use a [developer console](info:devtools) to run code, please note that it doesn't `use strict` by default.

Sometimes, when `use strict` makes a difference, you'll get incorrect results.

So, how to actually `use strict` in the console?

First, you can try to press `key:Shift+Enter` to input multiple lines, and put `use strict` on top, like this:

```js
'use strict'; <Shift+Enter for a newline>
//  ...your code
<Enter to run>
```

It works in most browsers, namely Firefox and Chrome.

If it doesn't, e.g. in an old browser, there's an ugly, but reliable way to ensure `use strict`. Put it inside this kind of wrapper:

```js
(function() {
  'use strict';

  // ...your code here...
})()
```

## Should we "use strict"?

The question may sound obvious, but it's not so.

One could recommend to start scripts with `"use strict"`... But you know what's cool?

Modern JavaScript supports "classes" and "modules" - advanced language structures (we'll surely get to them), that enable `use strict` automatically. So we don't need to add the `"use strict"` directive, if we use them.

**So, for now `"use strict";` is a welcome guest at the top of your scripts. Later, when your code is all in classes and modules, you may omit it.**

As of now, we've got to know about `use strict` in general.

In the next chapters, as we learn language features, we'll see the differences between the strict and old modes. Luckily, there aren't many and they actually make our lives better.

All examples in this tutorial assume strict mode unless (very rarely) specified otherwise.
