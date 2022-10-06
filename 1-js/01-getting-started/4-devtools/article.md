# Иштеп чыгуучунун консолу

Код каталарга шыктуу. Балким сиз коддо ката кетиресиз... Апей, мен эмнени айтып жатам? Сиз *шексиз* ката кетиресиз, акыры эгер [робот](https://en.wikipedia.org/wiki/Bender_(Futurama)) эмес, адам болсоңуз.

Бирок браузерде колдонуучулар демейки боюнча каталарды көрүшпөйт. Демек, скриптте бир нерсе туура эмес болуп кетсе, эмне бузулганын көрбөйбүз жана аны оңдой албайбыз.

Каталарды көрүү жана скрипттер жөнүндө башка көптөгөн пайдалуу маалыматтарды алуу үчүн браузерлерде "Иштеп чыгуучунун куралдары" (Developer tools же кыскача - devtools) камтылган.

Көпчүлүк программисттер иштеп чыгуу үчүн Chrome же Firefox'ту көздөшөт, анткени ошол браузерлерде эң мыкты иштеп чыгуучунун куралдары бар. Башка браузерлер да иштеп чыгуучунун куралдарын камсыздайт, кээде өзгөчө мүмкүнчүлүктөрү менен, бирок, адатта, Chrome же Firefox үчүн "кууп" ойношот. Ошентип, дээрлик бардык программисттердин "сүйүктүү" браузери бар жана көйгөй браузерге тиешелүү болсо, башкаларга которулушат.

Иштеп чыгуучунун куралдары күчтүү; алар көп мүмкүнчүлүктөргө ээ. Баштоо үчүн, биз аларды кантип ачууну, каталарды карап, JavaScript буйруктарын иштетүүнү үйрөнөбүз.

## Google Chrome

[bug.html](bug.html) баракчасын ачыңыз.

Андагы JavaScript кодунда ката бар. Ал кадимки келүүчүлөрдүн көзүнөн жашырылган, андыктан аны көрүү үчүн иштеп чыгуучунун куралдарын ачалы.

`key:F12` басыңыз же, Mac'ты колдонсоңуз, `key:Cmd+Opt+J` басыңыз.

Иштеп чыгуучунун куралдары демейки боюнча Console салмасында ачылат.

Бул мындай көрүнөт:

![chrome](chrome.png)

The exact look of developer tools depends on your version of Chrome. It changes from time to time but should be similar.

- Here we can see the red-colored error message. In this case, the script contains an unknown "lalala" command.
- On the right, there is a clickable link to the source `bug.html:12` with the line number where the error has occurred.

Below the error message, there is a blue `>` symbol. It marks a "command line" where we can type JavaScript commands. Press `key:Enter` to run them.

Now we can see errors, and that's enough for a start. We'll come back to developer tools later and cover debugging more in-depth in the chapter <info:debugging-chrome>.

```smart header="Multi-line input"
Usually, when we put a line of code into the console, and then press `key:Enter`, it executes.

To insert multiple lines, press `key:Shift+Enter`. This way one can enter long fragments of JavaScript code.
```

## Firefox, Edge жана башкалар

Most other browsers use `key:F12` to open developer tools.

The look & feel of them is quite similar. Once you know how to use one of these tools (you can start with Chrome), you can easily switch to another.

## Safari

Safari (Mac browser, not supported by Windows/Linux) is a little bit special here. We need to enable the "Develop menu" first.

Open Preferences and go to the "Advanced" pane. There's a checkbox at the bottom:

![safari](safari.png)

Now `key:Cmd+Opt+C` can toggle the console. Also, note that the new top menu item named "Develop" has appeared. It has many commands and options.

## Корутунду

- Developer tools allow us to see errors, run commands, examine variables, and much more.
- They can be opened with `key:F12` for most browsers on Windows. Chrome for Mac needs `key:Cmd+Opt+J`, Safari: `key:Cmd+Opt+C` (need to enable first).

Now we have the environment ready. In the next section, we'll get down to JavaScript.
