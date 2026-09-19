# Solarchik

Voice AI friend you carry everywhere — talks in the room, runs with you, takes the call when you cannot.

**MunichTech EXPO 2026 · Open AI & DeepTech Grand Challenge**  
Team **Solar DePin** · Vadym Bilobrovets · Ukraine

## One character, three modes

1. **Friend** — in his room you talk by voice or text. He answers in your language, with a voice you pick at first setup.
2. **Runner** — in the roof run he stays with you. Short spoken lines about the run. Mic is tap-to-talk so he does not interrupt a live conversation.
3. **Secretary** — tap the red phone in the booth. He logs who called, why, urgency, and the next action, then speaks the report.

Not a chatbot in a blank window. A small solar robot with a room, a game, and a desk.

## Problem

Most apps are silent screens. Games do not talk back. Assistants sit in a separate chat and know nothing about what you are doing. People want one companion that stays with them in play and in real life.

## Solution

Solarchik is that companion.

- Room chat + hold-free tap microphone
- Roof runner with voice banter on a 30–40s cadence, silenced while the player is mid-conversation
- Phone-booth secretary desk: on/off, call notes, archive, contacts, session credit
- Same voice and personality across all three modes

## What judges should open

| Piece | Link |
|---|---|
| This branch | [munichtech-expo](https://github.com/mcBanCh/solarchik-munichtech-2026/tree/munichtech-expo) |
| Demo video | paste your YouTube URL in `SUBMISSION.md` |
| Live web | Grok App Builder preview / solardepin.net when public |

## Stack

- React + TypeScript UI (room, runner HUD, secretary desk)
- Gemini primary replies, OpenAI / Featherless fallback
- Android `SpeechRecognizer` in the APK, Web Speech API on web
- On-device TTS for the chosen voice
- No API keys in this repo. Models run behind a server or native bridge.

## Architecture

```
Player voice
    │
    ▼
Speech-to-text (Android / web)
    │
    ▼
Solarchik brain (Gemini → fallback)
    │
    ├── room chat (1–2 spoken sentences)
    ├── runner line (one sentence, same voice)
    └── secretary report (who / why / next action)
    │
    ▼
TTS out + on-screen caption
```

## Repo layout

```
README.md          this file
SUBMISSION.md      MunichTech form copy (problem / solution / disclosure)
PITCH.md           90-second spoken pitch
```

Source for the playable client lives with the Solar DePin CLOCK IN build. This branch is the public MunichTech submission surface: product story, architecture, and links judges can open tonight.

## Built by

Solar DePin (Vadym) · [X @SolarDePin](https://x.com/SolarDePin) · [solardepin.net](https://solardepin.net)
