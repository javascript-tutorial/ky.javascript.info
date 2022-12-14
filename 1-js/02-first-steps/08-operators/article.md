# Базалык операторлор, математика

Көптөгөн операторлор бизге мектептен таанымал, булар кошуу `+`, көбөйтүү `*`, кемитүү `-` ж.б.

Бул бөлүмдө биз жөнөкөй операторлордон баштайбыз, андан кийин мектептеги арифметикада окутулбаган JavaScript спецификалык аспектилерине топтолобуз.

## Терминдер: "унардык", "бинардык", "операнд"

Улантуудан мурун, кээ бир жалпы терминологияны түшүнүп алалы.

- *Операнд* -- операторлор колдонулган нерсе. Мисалы үчүн, `5 * 2` көбөйтүүсүндө эки оператор бар: сол операнд `5` жана оң операнд `2`. Кээде буларды "операнддардын" ордуна "аргументтер" деп аташат.
- Оператор бир операндга ээ болсо, ал *унардык* болот. Мисалы, унардык минус `-` сандын белгисин өзгөртөт:

    ```js run
    let x = 1;

    *!*
    x = -x;
    */!*
    alert( x ); // -1, унардык минус колдонулду
    ```
- Оператор эки операндга ээ болсо, ал *бинардык* болот. Ошол эле минус бинардык формада да бар:

    ```js run no-beautify
    let x = 1, y = 3;
    alert( y - x ); // 2, бинардык минус маанилерди кемитет
    ```

    Формалдуу түрдө жогорудагы мисалдарда бир эле белги менен белгиленген эки ар кандай оператор бар: тануу оператору -- сандын белгисин өзгөртүүчү унардык оператор жана кемитүү оператору -- бир санды экинчисинен кемите турган бинардык оператор.

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

Бул жерде операторлор биринин артынан бири иштешет. Биринчи `+` эки санды кошот, андыктан ал `4`'тү кайтарат, андан кийин кийинки `+` ага `1` сабын кошот, демек, натыйжада `4 + '1' = '41'` болот.

```js run
alert('1' + 2 + 2); // "122", "14" эмес
```

Бул жерде биринчи операнд -- бул сап, компилятор башка эки операндды да сап катары карайт. `2` операнды `'1'` менен бириктирилет, ошондуктан натыйжада `'1' + 2 = "12"`, андан кийин `"12" + 2 = "122"` болот.

Бинардык `+` гана саптар менен ушундай иштейт. Башка арифметикалык операторлор сандар менен гана иштешет жана операнддарын ар дайым сандарга айландырышат.

Мисалы, кемитүү жана бөлүү:

```js run
alert( 6 - '2' ); // 4, '2' санга айландырылат
alert( '6' / '2' ); // 3, эки операнд тең сапка айландырылат
```

## Санга келтирүү, унардык +

Плюс `+` эки формада бар: биз жогоруда колдонгон бинардык форма жана унардык форма.

Унардык плюс же, башкача айтканда, плюс оператору `+` бир мааниге колдонулат, сандарга эч нерсе кылбайт. Бирок эгерде операнд сан болбосо, унардык плюс аны санга айландырат.

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

Саптарды сандарга айландыруу зарылдыгы абдан көп пайда болот. Мисалы, адатта HTML форманын талааларынын маанилери сап түрүндө болот. Аларды суммалайлы десек эмне кылыш керек?

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
// эки маани бинардык плюсту колдонуудан мурун сандарга айландырылат
alert( +apples + +oranges ); // 5
*/!*

// узунураак вариант
// alert( Number(apples) + Number(oranges) ); // 5
```

Математиктин көз карашы боюнча, плюстардын көптүгү кызыктай көрүнүшү мүмкүн. Бирок программисттин көз карашы боюнча, бул жерде өзгөчө эч нерсе жок: адегенде унардык плюстар колдонулат, алар саптарды сандарга айландырат, андан кийин бинардык плюс аларды жыйынтыктайт.

Эмнеге маанилерге унардык плюстар бинардык плюстардан мурун колдонулат? Төмөндө көрө турганыбыздай, бул алардын алгачкылыгына байланыштуу.

## Операторлордун алгачкылыгы

Эгерде туюнтма бирден ашык операторго ээ болсо, аткаруу тартиби алардын *алгачкылыгы* же башкача айтканда, оператордук биринчиликтин демейки тартиби менен аныкталат.

`1 + 2 * 2` туюнтмасындагы көбөйтүүнү кошууга чейин эсептөө керек экенин мектептен биз баарыбыз билебиз. Алгачкылык дал ушул нерсе. 
Көбөйтүү кошууга караганда *жогору алгачкылыкка* ээ болот деп айтылат.

Кашаалар кандайдыр бир алгачкылыктан бийик турат, андыктан демейки тартип бизди канааттандырбаса, аларды өзгөртүү үчүн кашааларды колдоно алабыз. Мисалы, `(1 + 2) * 2`.

JavaScript'те көптөгөн операторлор бар. Ар бир оператордун ылайыктуу алгачкылык номуру бар. Саны көбүрөөк болгон оператор биринчи аткарылат. Эгерде алгачкылык бирдей болсо, анда солдон оңго карай аткарылат.

Мына [алгачкылык жадыбалынан](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) үзүндү (баарын жаттап алуунун кереги жок, бирок унардык операторлордун алгачкылыгы ылайыктуу бинардык операторлорго караганда жогору экенин эске алыңыз):

| Алгачкылык | Аталыш | Белги |
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

Көрүнүп тургандай, "унардык плюс" `14` алгачкылыгына ээ, ал "кошуунун" (бинардык плюстун) алгачкылыгынан -- `11`ден жогору. Мына ошондуктан `"+apples + +oranges"` туюнтмасында унардык плюс кошуудан мурун аткарылат.

## Ыйгаруу

Ыйгаруу `=` да оператор экенин белгилей кетели. Ал алгачкылык жадыбалында өтө төмөн `2` алгачкылыгы менен келтирилген.

Ошондуктан, биз өзгөрмөгө маани ыйгарганыбызда, мис. `x = 2 * 2 + 1`, адегенде эсептөөлөр аткарылып, андан кийин ыйгаруу `=` аткарылып, натыйжа `x` өзгөрмөсүндө сакталат.

```js
let x = 2 * 2 + 1;

alert( x ); // 5
```

### Ыйгаруу = маанини кайтарат

`=` "сыйкырдуу" тил түзүлүшү эмес, оператор экенинин фактысы кызыктуу мааниге ээ.

JavaScript'теги бардык операторлор маанини кайтарышат. Бул `+` жана `-` үчүн айкын, бирок `=` үчүн да дурус.

`x = value` чакыруусу `value`'ну `x` ичине жазат *жана аны кайтарат*.

Бул жерде ыйгарууну татаалыраак туюнтманын бир бөлүгү катары колдонгон демонстрация келтирилген:

```js run
let a = 1;
let b = 2;

*!*
let c = 3 - (a = b + 1);
*/!*

alert( a ); // 3
alert( c ); // 0
```

Жогорудагы мисалда `(a = b + 1)` туюнтмасынын натыйжасы `a` өзгөрмөсүнө ыйгарылган маани (б.а. `3`) болот. Андан кийин ал кийинки эсептөөлөр үчүн колдонулат.

Укмуштай код, туурабы? Биз анын кантип иштээрин түшүнүшүбүз керек, анткени кээде биз аны JavaScript китепканаларынан көрө алабыз.

Бирок, сураныч, мындай код жазбаңыз. Бул трюктар, албетте, кодуңузду түшүнүктүү же окула тургандай кылбайт.

### Чынжырча ыйгаруусу

Дагы бир кызыктуу өзгөчөлүк - чынжырча ыйгаруу мүмкүнчүлүгү:

```js run
let a, b, c;

*!*
a = b = c = 2 + 2;
*/!*

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

Чынжырча ыйгаруулар оңдон солго карай аткарылат. Биринчиден, эң оң жактагы `2 + 2` туюнтмасы аткарылып, андан кийин сол жактагы өзгөрмөлөргө ыйгарылат: `c`, `b` жана `a`. Аягында, бардык өзгөрмөлөр бир жалпы мааниге ээ болот.

Дагы бир жолу, окууга ыңгайлуу болуу үчүн мындай кодду бир нече сапка бөлүү жакшыраак:

```js
c = 2 + 2;
b = c;
a = c;
```

Айрыкча кодду тез карап жатканда, муну окууга оңоюраак.

## "Өзгөртүү жана ыйгаруу" оператору

Биз көп учурда өзгөрмөгө операторду колдонушубуз керек жана жаңы натыйжаны ошол эле өзгөрмөдө сакташыбыз керек.

Мисалы:

```js
let n = 2;
n = n + 5;
n = n * 2;
```

Бул жазууну `+=` жана `*=` операторлорунун жардамы менен кыскартууга болот:

```js run
let n = 2;
n += 5; // эми n = 7 (n = n + 5 менен бирдей)
n *= 2; // эми n = 14 (n = n * 2 менен бирдей)

alert( n ); // 14
```

Кыска "өзгөртүү жана ыйгаруу" операторлору бардык арифметикалык жана биттик операторлор үчүн бар: `/=`, `-=` ж.б.

Мындай операторлор кадимки ыйгаруу сыяктуу эле алгачкылыкка ээ, андыктан алар башка көптөгөн эсептөөлөрдөн кийин аткарылат:

```js run
let n = 2;

n *= 3 + 5; // алгач оң бөлүгү эсептелинет, n *= 8 менен бирдей

alert( n ); // 16  
```

## Инкремент/декремент

<!-- Can't use -- in title, because the built-in parser turns it into a 'long dash' – -->

Санды бирге көбөйтүү же азайтуу эң кеңири таралган сандык операциялардын бири болуп саналат.

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
Инкремент/декремент өзгөрмөлөргө гана колдонулушу мүмкүн. Аны `5++` сыяктуу мааниде колдонууга аракет кылуу катага алып келет.
```

`++` жана `--` операторлору өзгөрмөнүн алдында же өзгөрмөдөн кийин жайгаштырылышы мүмкүн.

- Оператор өзгөрмөдөн кийин келгенде, ал "постфикс формасында" болот: `counter++`.
- "Префикс формасы" оператор өзгөрмөнүн алдына келгенде болот: `++counter`.

Бул эки нускама тең бирдей нерсени аткарат: `counter` өзгөрмөсүн `1`ге көбөйтөт.

Айырмасы барбы? Ооба, бирок биз аны `++/--` кайтарган маанисин колдонсок гана көрө алабыз.

Келгиле, тактап алалы. Белгилүү болгондой, бардык операторлор маанини кайтарышат. Инкремент/декремент да бөтөнчө эмес. Префикс формасы жаңы маанини кайтарат, ал эми постфикс формасы эски маанини кайтарат (санды көбөйтүүгө/азайтууга чейин).

Айырмасын көрүү үчүн, мисал келтирели:

```js run
let counter = 1;
let a = ++counter; // (*)

alert(a); // *!*2*/!*
```

`(*)` сабында *префикс* формасы `++counter` `counter`'ди көбөйтөт жана жаңы `2` маанисин кайтарат. Ошентип, `alert` `2`ни көрсөтөт.

Эми постфикс формасын колдонолу:

```js run
let counter = 1;
let a = counter++; // (*) ++counter counter++'ка алмашты

alert(a); // *!*1*/!*
```

`(*)` сабында *постфикс* формасы `counter++` да `counter`'ди көбөйтөт, бирок *эски* (көбөйтүүгө чейинки) маанисин кайтарат. Ошентип, `alert` `1`ди көрсөтөт.

Жыйынтыктайлы:

- Эгерде көбөйтүүнүн/азайтуунун натыйжасы колдонулбаса, анда кайсы форманы колдонуунун айырмасы жок:

    ```js run
    let counter = 0;
    counter++;
    ++counter;
    alert( counter ); // 2, жогорудагы саптар бирдей нерсени кылышты
    ```
- Эгерде биз маанини көбөйтүүнү *жана* оператордун натыйжасын колдонууну кааласак, бизге префикс формасы керек:

    ```js run
    let counter = 0;
    alert( ++counter ); // 1
    ```
- Эгерде биз маанини көбөйтүүнү, бирок анын мурунку маанисин колдонууну кааласак, бизге постфикс формасы керек:

    ```js run
    let counter = 0;
    alert( counter++ ); // 0
    ```

````smart header="Башка операторлордун арасындагы инкремент/декремент"
`++/--` операторлору туюнтмалардын ичинде да колдонулушу мүмкүн. Алардын алгачкылыгы башка арифметикалык операциялардын көбүнө караганда жогору.

Мисалы үчүн:

```js run
let counter = 1;
alert( 2 * ++counter ); // 4
```

Төмөндөгү менен салыштырыңыз:

```js run
let counter = 1;
alert( 2 * counter++ ); // 2, себеби counter++ "эски" маанисин кайтарат
```

Техникалык жактан түзүк болгону менен, мындай жазуу адатта коддун окулушун начарлатат. Бир сап көп нерсени аткарса -- бул жакшы эмес.

Кодду окуп жатканда, тез "вертикалдуу" сканерлөө `counter++` сыяктуу нерселерди оңой эле өткөрүп жибериши мүмкүн жана өзгөрмө жогорулатылганы анык болбойт.

Биз "бир сап -- бир иш-аракет" стилин сунуштайбыз:

```js run
let counter = 1;
alert( 2 * counter );
counter++;
```
````

## Биттик операторлор

Биттик операторлор аргументтерди 32-биттик бүтүн сандар катары карашат жана алардын экилик көрсөтүм деңгээлинде иштешет.

Бул операторлор JavaScript үчүн спецификалуу эмес. Алар көпчүлүк программалоо тилдеринде колдоого алынат.

Операторлордун тизмеси:

- AND(жана) ( `&` )
- OR(же) ( `|` )
- XOR(биттик бөтөнчөлөгөн же) ( `^` )
- NOT(эмес) ( `~` )
- LEFT SHIFT(солго жылдыруу) ( `<<` )
- RIGHT SHIFT(оңго жылдыруу) ( `>>` )
- ZERO-FILL RIGHT SHIFT(нөлдөр менен толтуруу менен оңго жылдыруу) ( `>>>` )

Биз сандар менен эң төмөнкү (биттик) деңгээлде иштеш керек болгондо бул операторлор өтө сейрек колдонулат. Жакын арада бизге бул операторлордун кереги жок, анткени веб иштеп чыгуучулар аларды аз колдонушат, бирок криптография сыяктуу кээ бир өзгөчө тармактарда алар пайдалуу болот. Зарылчылык жаралганда MDN'деги [Bitwise Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#bitwise_operators) бөлүмүн окуй аласыз.

## Үтүр

Үтүр оператору `,` эң сейрек кездешүүчү жана адаттан тыш операторлордун бири. Кээде ал кыскараак код жазуу үчүн колдонулат, андыктан эмне болуп жатканын түшүнүү үчүн аны билишибиз керек.

Үтүр оператору бизге бир нече туюнтмаларды үтүр `,` менен бөлүп аткарууга мүмкүндүк берет. Алардын ар бири аткарылат, бирок акыркысынын натыйжасы гана кайтарылат.

Мисалы:

```js run
*!*
let a = (1 + 2, 3 + 4);
*/!*

alert( a ); // 7 (3 + 4 эсептөөсүнүн жыйынтыгы)
```

Бул жерде биринчи `1 + 2` туюнтмасы аткарылат жана анын натыйжасы ыргытылат. Андан кийин `3 + 4` аткарылат жана натыйжа катары кайтарылат.

```smart header="Үтүр өтө төмөн алгачкылыкка ээ"
Сураныч, үтүр операторунун алгачкылыгы `=` операторунан абдан төмөн экенин эске алыңыз, андыктан жогорудагы мисалда кашаалар маанилүү.

Кашааларсыз `a = 1 + 2, 3 + 4` туюнтмасында адегенде `+` операторлору аткарылып, сандарды `a = 3, 7` менен бириктирет, андан кийин ыйгаруу оператору `=` `a = 3`'тү ыйгарат, ал эми калганы көңүлдөнбөйт. Бул `(a = 1 + 2), 3 + 4` менен бирдей.
```

Эмне үчүн бизге акыркы туюнтмадан башкасынын баарын ыргыткан оператор керек?

Кээде адамдар бир сапка бир нече иш-аракеттерди киргизүү үчүн аны татаал түзүлүштөрдө колдонушат.

Мисалы:

```js
// бир сапта үч операция
for (*!*a = 1, b = 3, c = a * b*/!*; a < 10; a++) {
 ...
}
```

Мындай трюктар көптөгөн JavaScript фреймворкторунда колдонулат. Ошондуктан биз аларды белгилеп жатабыз. Бирок, адатта, алар коддун окулушун жакшыртпайт, андыктан аларды колдонуудан мурун жакшылап ойлонушубуз керек.
