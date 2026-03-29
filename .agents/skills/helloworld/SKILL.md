---
name: helloworld
description: Translate helloworld to another language, and generate audio if the user requests.
---

# Helloworld

## When to use this skill
Use this skill when the user sends 1) "helloworld" and only "helloworld", or 2) "helloworld (audio)".

## Terminologies

- Language name, or `lang_name` in some cases: the human-readable name of the language in English, for example `English`, `Spanish`, or `Chinese`.
- Language ID, or `lang_id` in some cases: the ISO 639 language code used by the system, for example `en`, `es`, or `zh`.

## How to Translate
Return in the format `text (language name)`. The `text` part is the text of "helloworld" in another language.

1. If audio isn't requested, then it's up to you to pick the targeting language so that each time the user gets a random response.
2. Otherwise when audio is requested, return `text (language name)` first, but the language is limited, see [references/LANGS.md] for allowed languages. And then use `text` and `lang_id` as parameters to generate an audio file, see [references/TTS.md] for details.

## Output Example

- `你好世界 (Chinese)`
- `Привет, мир (Russian)`
