# Lengo dictionary packs

Offline learner's-dictionary packs for the Lengo iOS app:
16 languages, words placed in twelve learning bands (A1.1 … C2.2). The app downloads
them from this repository's releases. This repository holds data only.

**Release 2026.10.6**, built from the English Wiktionary dump of
2026-09-02.

| Language | Words | Entries | Entries with translations | Levels | Installed | Download |
|---|---:|---:|---:|---|---:|---:|
| German (`de`) | 10,994 | 11,427 | 86% | estimated from word frequency | 6.5 MB | 2.1 MB |
| English (`en`) | 8,909 | 10,390 | 91% | CEFR-J 1.5 (A1–B2) and Octanove (C1–C2) lists | 8.4 MB | 2.7 MB |
| French (`fr`) | 10,997 | 11,710 | 90% | estimated from word frequency | 6.5 MB | 2.1 MB |
| Spanish (`es`) | 10,993 | 11,917 | 90% | estimated from word frequency | 6.9 MB | 2.1 MB |
| Arabic (`ar`) | 11,000 | 13,009 | 68% | estimated from word frequency | 8.4 MB | 2.1 MB |
| Turkish (`tr`) | 10,565 | 11,078 | 79% | estimated from word frequency | 8.6 MB | 2.1 MB |
| Italian (`it`) | 10,963 | 11,840 | 82% | estimated from word frequency | 6.3 MB | 1.9 MB |
| Portuguese (`pt`) | 10,982 | 11,901 | 87% | estimated from word frequency | 7.1 MB | 2.2 MB |
| Russian (`ru`) | 10,998 | 11,330 | 87% | estimated from word frequency | 5.8 MB | 1.9 MB |
| Chinese (Simplified) (`zh-CN`) | 10,917 | 11,945 | 62% | estimated from word frequency | 4.9 MB | 1.6 MB |
| Japanese (`ja`) | 10,999 | 13,523 | 54% | estimated from word frequency | 6.8 MB | 1.8 MB |
| Korean (`ko`) | 10,999 | 12,248 | 60% | estimated from word frequency | 4.2 MB | 1.3 MB |
| Dutch (`nl`) | 10,996 | 11,648 | 82% | estimated from word frequency | 5.2 MB | 1.7 MB |
| Polish (`pl`) | 10,867 | 11,354 | 82% | estimated from word frequency | 8.2 MB | 2.2 MB |
| Swedish (`sv`) | 7,817 | 8,085 | 87% | Kelly list | 4.7 MB | 1.5 MB |
| Hindi (`hi`) | 9,216 | 9,938 | 69% | estimated from word frequency | 4.8 MB | 1.3 MB |

All sixteen packs: 103 MB installed, 31 MB to download. The app also ships
a starter pack with bands A1.1–A1.2 of every language (15,451 entries,
9.9 MB).

Full coverage tables, per-band counts and format measurements: [`report.md`](report.md).

## What the levels mean

- The .1 and .2 steps split each CEFR level for practice. **They are Lengo's own
  steps, not official CEFR levels.**
- English (CEFR-J Wordlist, Octanove Vocabulary Profile) and Swedish (Kelly list) hold
  exactly the words of those published CEFR-labelled lists, with their levels. For the
  other fourteen languages the band is **an estimate from word frequency** (wordfreq);
  each entry records which applies (`band_source` 9 = estimated).
- Meanings share their word's band: no open source gives levels per meaning.

## What a pack contains

One read-only SQLite database per language (`PRAGMA user_version` = schema version),
compressed with xz. `manifest.json` lists every pack's size and SHA-256 (compressed and
unpacked), entry and band counts.

- `entry`: headword, part of speech, band, band source, frequency rank, gender, reading
  (pinyin, kana, vowelled Arabic, stressed Russian, romanised Hindi and Korean), IPA.
- `sense`: up to six short English meanings; `example`: Wiktionary usage examples
  with English translations (quotations from books and songs are left out).
- `term`: search keys for headwords, inflected forms and readings.
- `concept`, `entry_concept`: translations. A concept is one sense of an English word
  that has a Wiktionary translation table; two entries in different packs that link to
  the same concept translate each other. Each word is stored once, in its own pack.

## Known gaps

- Bands outside English and Swedish are frequency estimates, and frequencies are a 2021
  snapshot. English and Swedish cover only their lists' words (about 9,000 and 8,000). Hindi, Korean and Turkish frequency lists are shorter, so their highest
  bands are thinner.
- Translations exist only where Wiktionary's translation tables list a word: about
  half of Chinese, Japanese and Korean entries have one, more for European languages.
- Meanings are in English only.
- Lemmas are chosen automatically from frequency lists; some rare homographs and
  dialect words remain. Report problems in this repository's issues.

## Licence and attribution

The packs are licensed under [CC BY-SA 4.0](LICENSE). See [ATTRIBUTION.md](ATTRIBUTION.md).
