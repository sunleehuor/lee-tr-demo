# lee-tr-cli

> A CLI tool to help translate keys **one by one automatically** into multiple languages  
> Supports **JSON**, **ES module**, and **CommonJS** formats.

`lee-tr-cli` is designed for developers who manage multiple language files  
(e.g. `en`, `km`, `jp`, …) and want to translate once and apply everywhere.

> *Requirement `Node Js` (`^20.*`)

---

## What does `lee-tr-cli` do?

- Translate text into **multiple languages at once**
- No need to translate manually language by language
- Works with:
  - JSON files
  - ES modules (`export default`)
  - CommonJS (`module.exports`)
- Can translate from:
  - Provided keys
  - Clipboard content (if no keys provided)

---

## 1. Installation

Install globally using npm:

```bash
npm install -g lee-tr-cli
```

## 2. Configuration

Create a configuration file at `lee-tr/config.json` with the following content:

```json
{
  "type": "module",
  "defaultLocale": "en",
  "locales": [
    {
      "lang": "en",
      "file": "en.ts"
    },
    {
      "lang": "km",
      "file": "km.ts"
    }
  ],
  "localePath": "module"
}
```

## 3. Configuration fields

| Field           | Description                                                                                   | Example                                                                    |
| --------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `type`          | Translation file type. Options: `json`, `module`, `commonjs`                                  | `"module"`                                                                 |
| `defaultLocale` | Default language used when translating from clipboard content                                 | `"en"`                                                                     |
| `locales`       | Array of target language files. Each object has `lang` (language code) and `file` (file name) | `[ { "lang": "en", "file": "en.ts" }, { "lang": "km", "file": "km.ts" } ]` |
| `localePath`    | Directory path where translation files are stored                                             | `"module"`                                                                 |

## 4. Folder structures

```bash
project/
├─ module/
│  ├─ en.ts
│  └─ km.ts
└─ lee-tr/config.json

```

## 5. Usage and work flow
- options: `t, ...`
```bash
lee-tr [options] [keys]
```
Found a bug or have an issue? Please report it here:  
👉 https://github.com/sunleehuor/lee-tr-cli
