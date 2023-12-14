# Заманбап JavaScript колдонмосу Кыргыз тилинде

Бул репозиторийде <https://javascript.info> колдонмосунун кыргыз тилиндеги котормосу сакталып жатат.


**Сиз кантип салым кошо аласыз:**

1. [Kyrgyz Translate Progress](https://github.com/javascript-tutorial/ky.javascript.info/issues/1) талкуулоосун караңыз.
2. Которгуңуз келген, белгиленбеген макаланы тандаңыз.
3. Ошол эле талкуулоого макаланын аталышы менен жорум кошуңуз, мисалы, `JavaScript'ке киришүү`. Ал макаланы сиз которуп жатканыңызды баары билиши үчүн, биздин ботубуз аны талкуулоодо белгилейт. Сиздин жорумуңуз макаланын аталышын гана камтышы керек.
4. Репозиторийди көчүрүңүз ("Fork" баскычын басыңыз), андан кийин бир макаланы которуп, бүткөндөн кийин, биригүү сурамын жөнөтүңүз (Pull Request). Сурамдын аталышы сиз которгон макаланын аталышына дал келиши керек. Кээ бир макалаларда тапшырмалар, сүрөттөр ж.б. камтылган кошумча файлдар бар. Аларды да которуу керек.

Сураныч, салым кошуучуларга котормоңузду карап чыгууга жана бириктирүүгө же өзгөртүүнү талап кылууга уруксат бериңиз.
   
If maintainers do not respond, or if you'd like to become a maintainer, write us at the [main repo](https://github.com/javascript-tutorial/en.javascript.info/issues/new).
    
**Let others know what you're translating, in message boards or chats in your language. Invite them to join!**

🎉 Thank you!

Your name and the contribution size will appear in the "About project" page when the translation gets published.

P.S. The full list of languages can be found at <https://javascript.info/translate>.

## Structure

Every chapter, an article or a task resides in its own folder.

The folder is named `N-url`, where `N` – is the number for sorting (articles are ordered), and `url` is the URL-slug on the site.

The folder has one of files:

- `index.md` for a section,
- `article.md` for an article,
- `task.md` for a task formulation (+`solution.md` with the solution text if any).

A file starts with the `# Title Header`, and then the text in Markdown-like format, editable in a simple text editor. 

Additional resources and examples for the article or the task, are also in the same folder.

## Translation Tips

Please keep line breaks and paragraphs "as is": don't add newlines and don't remove existing ones. Makes it easy to merge future changes from the English version into the translation. 

If you see that the English version can be improved – great, please send a PR to it.

### Terms

- Some specification terms are not to be translated, e.g. "Function Declaration" can be left "as is".
- For other terms like `resolved promise`, `slash`, `regexp`, and so on - look for a glossary, hopefully there's one for your language already. If not, look for translations in manuals, such as [MDN](https://developer.mozilla.org/en-US/).


### Terms with meaning

In English many terms have an obvious meaning. For a person who doesn't understand English, there's no such meaning.

Please keep that in mind, sometimes explanations or additional translations are needed, e.g.

```md
`ReadableStream` allows to read data chunk-by-chunk.
```

The class name `ReadableStream` has an obvious meaning for those who understand English.

Some people who read translations may not know English so well. So we can add a translation of `ReadableStream` in parentheses, like this (Spanish below):

```md
`ReadableStream` ("flujo legible") permite leer datos fragmento por fragmento. 
```

### Text in Code Blocks

- Translate comments.
- Translate user-messages and example strings.
- Don't translate variables, classes, identifiers.
- Ensure that the code works after the translation :)

Example:

```js
// Example
const text = "Hello, world";
document.querySelector('.hello').innerHTML = text;
```

✅ DO (translate comment):

```js
// Ejemplo
const text = 'Hola mundo';
document.querySelector('.hello').innerHTML = text;
```

❌ DON'T (translate class):

```js
// Ejemplo
const text = 'Hola mundo';
// ".hello" is a class
// DO NOT TRANSLATE
document.querySelector('.hola').innerHTML = text;
```

Please note, that sometimes code is followed by pictures, and if you translate text `Hello` -> `Hola` in the code, you need to translate text in picturess as well.

In that case it's probably easier not to translate such text. See more about translating images later.


### External Links

If an external link is to Wikipedia, e.g. `https://en.wikipedia.org/wiki/JavaScript`, and a version of that article exists in your language that is of decent quality, link to that version instead.

Example:

```md
[JavaScript](https://en.wikipedia.org/wiki/JavaScript) is a programming language.
```

✅ OK (en -> es):

```md
[JavaScript](https://es.wikipedia.org/wiki/JavaScript) es un lenguaje de programación.
```

For links to MDN, a partially translated version is ok.

If a linked article has no translated version, leave the link "as is".

### Metadata

Some files, usually tasks, have YAML metadata at the top, delimited by `---`:

```md
importance: 5

---
...
```

Please don't translate "importance" (and other top metadata).

### Anchors

Some headers have `[#anchor]` at the end, e.g.

```md
## Spread operator [#spread-operator]
```

Please don't translate or remove the `[#...]` part, it's for URL anchors.


### Images

Most illustrations use SVG format, the text in there can be replaced with a translated variant.

The translated text is in `images.yml` file in the tutorial root.

The file format is YAML:
```yaml
image.svg:        # image file
  "hello world":  # English phrase
    text: "Hola mundo"  # translation
    position: "centre"  # "center" or "right", if needed to center or right-align the translation
```

## Running locally

You can run the tutorial server locally to see how the translation looks.

The server and install instructions are at <https://github.com/javascript-tutorial/server>. 
