# Translating GARealistic

Thank you! You do not need the app's source code, only a text editor (VS Code recommended) and a GitHub account.

## 1. Pick or create your language file

- Your language already has a file (e.g. `pt-BR.json`)? Open it.
- Not there yet? Ask the maintainer to create it (they run `lang-publish --init <code> "<native name>"`), or copy `en.json`, rename it
  `<code>.json` (`pt-BR`, `es`, `ru`, ...), set `"_name"` to your language's own name (e.g. `"Português (Brasil)"`) and **clear every value to `""`**.

## 2. Translate

Each line is `"key": "text"`:

```json
"settings.language.title": "Idioma",
"settings.language.restart": "Reiniciar agora",
```

- **Only change the text on the right.** Never change a key (the part on the left).
- **Leave a line as `""` if you are not sure** - the app then shows the English text. Do not copy the English in.
- Keep placeholders exactly as they are: `{0}`, `{1}` stand for numbers or names filled in by the app. They may move around in the sentence
  but the same ones must be present. A line whose placeholders do not match English is ignored by the app.
- Keep punctuation conventions natural for your language. Text is written in natural case: the app upper-cases the labels that are shown in capitals.
- Keep the file valid JSON: straight double quotes, a comma after every line except the last, `\"` for a quote inside text, `\n` for a line break.
- Product names stay as they are: GARealistic, SimBrief, VATSIM, MSFS, FSEconomy, SayIntentions.

### Keys that look like `checklistItems.parkingBrakeSet~c53efa00`

Long lists of built-in text (checklist items) use keys derived from the English wording: `area.words~hash`. They are translated like any other line. If the English wording of such a line is later changed, its key changes too and the line appears again as empty in your file - your old translation no longer matches the new wording, so it is dropped on purpose.

### Formatting tags

Some longer help texts contain a few tags: `<b>bold</b>`, `<strong>`, `<accent>`, `<code>a path</code>`, `<br/>` (line break) and `<a href="https://...">a link</a>`. **Keep every tag exactly as in English** (you may move the words, and the tags around them, to suit your grammar). Do not translate what is inside `<code>...</code>` (file paths) and never change a link address: a line whose tags or links differ from English is ignored by the app. To show a literal `<` or `&` write `&lt;` / `&amp;`.

### Plurals

Counts have several keys, one per grammatical form, for example:

```json
"logbook.flights.one":   "{0} voo",
"logbook.flights.other": "{0} voos",
```

Provide every form your language needs (the maintainer's tool lists what is missing): English/Spanish/Portuguese use `one` and `other`;
Russian needs `one` (1, 21, 31...), `few` (2-4, 22-24...), `many` (5-20, 25-30...) and `other` (fractions). A form may leave out `{0}`.

## 3. Test it (optional but great)

1. Close GARealistic.
2. Copy your file to `%APPDATA%\GARealistic\lang\custom\<code>.json` (create the folders if needed).
3. In the app: Settings -> Language -> pick your language -> Restart now.
4. Lines the app rejected are listed in `%APPDATA%\GARealistic\session.log` (search for `[Loc`).

## 4. Send it

Open a pull request with your language file. Please change **only your own `<code>.json`**. The maintainer will review and publish it.
When new text is added to the app, your file gets new empty lines at the bottom of the next update - fill in what you can.
