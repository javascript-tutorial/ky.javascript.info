# Иштеп чыгуучунун консолу

Код каталарга шыктуу. Балким сиз коддо ката кетиресиз... Апей, мен эмнени айтып жатам? Сиз *шексиз* ката кетиресиз, акыры эгер [робот](https://en.wikipedia.org/wiki/Bender_(Futurama)) эмес, адам болсоңуз.

Бирок колдонуучулар браузерде демейки боюнча каталарды көрүшпөйт. Демек, скриптте бир нерсе туура эмес болуп кетсе, эмне бузулганын көрбөйбүз жана аны оңдой албайбыз.

Каталарды көрүү жана скрипттер жөнүндө башка көптөгөн пайдалуу маалыматтарды алуу үчүн браузерлерде "Иштеп чыгуучунун куралдары" (Developer tools же кыскача - devtools) камтылган.

Көпчүлүк программисттер иштеп чыгуу үчүн Chrome же Firefox'ту көздөшөт, анткени ошол браузерлерде эң мыкты иштеп чыгуучунун куралдары бар. Башка браузерлер да иштеп чыгуучунун куралдарын камсыздайт, кээде өзгөчө мүмкүнчүлүктөрү менен, бирок, адатта, Chrome же Firefox үчүн "кууп" ойношот. Ошентип, дээрлик бардык программисттердин "сүйүктүү" браузери бар жана көйгөй браузерге тиешелүү болсо, башкаларга которулушат.

Иштеп чыгуучунун куралдары күчтүү; алар көп мүмкүнчүлүктөргө ээ. Баштоо үчүн, биз аларды кантип ачууну, каталарды карап, JavaScript буйруктарын иштетүүнү үйрөнөбүз.

## Google Chrome

[bug.html](bug.html) баракчасын ачыңыз.

Андагы JavaScript кодунда ката бар. Ал кадимки келүүчүлөрдүн көзүнөн жашырылган, андыктан аны көрүү үчүн иштеп чыгуучунун куралдарын ачалы.

`key:F12` басыңыз же, Mac колдонсоңуз, `key:Cmd+Opt+J` басыңыз.

Иштеп чыгуучунун куралдары демейки боюнча Console салмасында ачылат.

Көрүнүшү:

![chrome](chrome.png)

Иштеп чыгуучу куралдардын так көрүнүшү Chrome версияңыздан көз каранды. Анда-санда өзгөрүп турат, бирок, жалпысынан, көрүнүшү мурунку версияларга окшош бойдон калууда.

- Консолдо биз кызыл түстөгү ката билдирүүсүн көрө алабыз. Бул учурда скрипт белгисиз "lalala" буйругун камтыйт.
- Оң жакта булак кодуна `bug.html:12` шилтемеси бар, анда бул ката пайда болгон код сызыгынын номуру көрсөтүлгөн.

Ката билдирүүсүнүн астында көк `>` белгиси бар. Ал JavaScript буйруктары териле турган "буйрук сабын" белгилейт. Аларды жүргүзүү үчүн `key:Enter` басыңыз.

Эми биз каталарды көрө алабыз, башталышы үчүн бул жетиштүү. Иштеп чыгуучунун куралдарына кийинчерээк кайтабыз жана дебаггингти (англис тилинен "debugging" - коддогу каталарды түзөтүү) <info:debugging-chrome> бөлүмүндө кененирээк карайбыз.

```smart header="Multi-line input"
Адатта, `key:Enter` басылганда, киргизилген код сабы дароо аткарылат.

Сапты которуу үчүн `key:Shift+Enter` басыңыз. Бул жол менен узунураак JavaScript кодун киргизүүгө болот.
```

## Firefox, Edge жана башкалар

Көпчүлүк браузерлерде иштеп чыгуучу куралдар `key:F12` басылганда ачылат.

Алардын көрүнүшү жана иштөө принциптери анча деле айырмаланбайт. Бул куралдардын бирин кантип колдонууну билгенден кийин (сиз Chrome менен баштасаңыз болот), башкасында оңой эле иштей аласыз.

## Safari


Safari (Mac браузери, Windows/Linux тарабынан колдоого алынбайт) бул жерде бир аз өзгөчө. Адегенде "Иштеп чыгуу менюсун" ("Developer menu") күйгүзүшүбүз керек.

Орнотууларды (Preferences) ачып, "Өркүндөтүлгөндөр" (Advanced) панелине өтүңүз. Төмөндө чекбокс бар:

![safari](safari.png)

Эми `key:Cmd+Opt+C` баскычтарын басуу менен консолду активдештирүүгө болот. Менюнун жаңы "Иштеп чыгуу" ("Develop") элементине да көңүл буруңуз. Анын көптөгөн буйруктары жана орнотуулары бар.

## Корутунду

- Иштеп чыгуучунун куралдары каталарды көрүүгө, буйруктарды аткарууга, өзгөрмөлөрдүн касиеттерин текшерүүгө ж.б. көп нерселерге мүмкүндүк берет.
- Аларды Windows'тун көпчүлүк браузерлеринде `key:F12` менен ачууга болот. Mac үчүн Chrome'до `key:Cmd+Opt+J`, Safari: `key:Cmd+Opt+C` (алгач күйгүзүү керек).

Эми биздин чөйрөбүз толук орнотулду. Кийинки бөлүмдө JavaScript'ке өтөбүз.
