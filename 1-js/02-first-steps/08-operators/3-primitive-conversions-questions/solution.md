
```js no-beautify
"" + 1 + 0 = "10" // (1)
"" - 1 + 0 = -1 // (2)
true + false = 1
6 / "3" = 2
"2" * "3" = 6
4 + 5 + "px" = "9px"
"$" + 4 + 5 = "$45"
"4" - 2 = 2
"4px" - 2 = NaN
"  -9  " + 5 = "  -9  5" // (3)
"  -9  " - 5 = -14 // (4)
null + 1 = 1 // (5)
undefined + 1 = NaN // (6)
" \t \n" - 2 = -2 // (7)
```

1. `"" + 1` сабы менен кошуу `1`'ди сапка айландырат: `"" + 1 = "1"`, анан бизде `"1" + 0` болот, ошол эле эреже колдонулат.
2. Кемитүү `-` (көпчүлүк математикалык операциялар сыяктуу) сандар менен гана иштейт, ал бош сапты `""` нөлгө `0` айландырат.
3. Сап менен кошуу `5` санын сапка айландырып, сапка кошот.
4. Кемитүү ар дайым сандарга айландырат, андыктан ал `"  -9  "`'ду `-9` санга айландырат (анын айланасындагы аралыктар көңүлдөнбөйт).
5. `null` сандык айландыруудан кийин `0` болуп калат.
6. `undefined` сандык айландыруудан кийин `NaN` болуп калат.
7. Саптын четтериндеги `\t` жана `\n` сыяктуу аралык символдору санга айландырылганда көңүлдөнбөйт, андыктан `" \t \n"` сабы бош сап сыяктуу, сандык айландыруудан кийин `0` болуп калат.
