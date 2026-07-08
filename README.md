# 🐾 小寵物中文練習店 — Little Pet Chinese Practice Shop

A gamified Traditional Chinese (繁體中文) character-practice app for kids.
Answer questions to earn coins, then spend them feeding, cleaning, and dressing up a virtual pet.

**Live app:** https://achen1219.github.io/zh-review-app_3/

## How it works

Each day the app presents a set of scheduled review characters (生字卡 flashcards with zhuyin,
radical, definition, and example phrases). After reviewing the cards, the child unlocks the
practice games and earns coins for correct answers. A daily goal of 30 questions keeps the
pet happy — skipping a day has consequences!

### Games

| Game | Skill practiced |
| --- | --- |
| ⚡ 快問快答 | Character/phrase meaning and fill-in-the-blank, against the clock |
| 🫧 泡泡快打 | Pop the bubble showing the target character — watch out for lookalikes |
| 🃏 配對遊戲 | Match characters to meanings |
| 🔊 讀音對決 | Heteronyms (破音字): pick the right pronunciation in context |
| 🔍 字形捉迷藏 | Visually confusable characters: find the right one |

### Features

- 🛍️ Pet shop with pets, food, baths, toys, clothes, and shoes
- 📖 Missed-answer review: get a question wrong and the flashcard comes back
- ☁️ Cross-device sync via a 6-character family code (Firebase Firestore)
- 📊 Parent dashboard with practice days, accuracy, and per-day history
- 📱 Installable as a home-screen app on iPad/Android (PWA manifest)

## Project structure

```
index.html          App shell, styles, and all game logic (vanilla JS, no build step)
game-data.js        Generated review schedule + per-character data (zhuyin, definitions, phrases)
confusable-data.js  Heteronym and confusable-character question banks
manifest.json       PWA manifest
icons/              App icons
fonts/              ToneOZ zhuyin font (WOFF2)
schedule.json       Source data used to generate game-data.js (not loaded by the app)
tzdict.json         Source dictionary used to generate game-data.js (not loaded by the app)
```

## Development

No build step — serve the folder with any static server:

```sh
python -m http.server 3456
# open http://localhost:3456
```

Progress is stored in `localStorage`; cloud sync only activates once a family code is created.

## Deployment

Pushes to `main` deploy automatically via GitHub Pages.
