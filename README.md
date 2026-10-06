# GARealistic translations

Language files for [GARealistic](https://garealistic.web.app) - the GA aircraft ownership, training and flight-tracking companion for MSFS 2024.
This repository holds **only** the text of the app, so you can translate it without any access to the source code.

| File | What it is |
|---|---|
| `en.json` | The English source text. **Do not edit** - it is generated and overwritten. |
| `pt-BR.json`, `es.json`, `ru.json`, ... | One file per language: `"key": "your translation"`. |
| `languages.json` | The list of languages with their coverage. Generated. |

Want a language that is not here? Open an issue or a pull request - see [CONTRIBUTING.md](CONTRIBUTING.md).

Translations are reviewed by the maintainer, then published: once published, the language appears in the app under
Settings -> Language (players download it from there, and it updates itself when you improve it). The app always falls back to English for
any line that is empty or missing, so a partial translation is fine and safe to ship.
