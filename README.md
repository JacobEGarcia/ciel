# CIEL — voice companion

A voice-first 3D companion who lives in your browser. Talk to her — she listens,
thinks, and speaks back, with a live animated face, emotions, and a memory of
the things you tell her.

**Live:** https://jacobegarcia.github.io/ciel/

## The voice loop

- **Listen** — Web Speech API (`SpeechRecognition`), push-to-talk (hold Space or
  tap the mic), live transcript, barge-in (start talking and she stops mid-sentence).
- **Think** — a free, keyless brain. Primary: the anonymous Pollinations text API.
  If the free link is down she falls back to a built-in offline personality so the
  conversation never dies (the settings console shows which brain answered).
- **Speak** — `speechSynthesis` with voice/rate/pitch controls, mouth envelope
  driven by word-boundary events plus a phoneme-ish oscillator, emotion tags in
  her replies (`[happy]`, `[surprised]`...) drive her face and poses.

## The character

Fully procedural Three.js (no model files): cel-shaded materials on a 3-step
gradient map, layered hair with spring physics, canvas-textured pleated skirt,
blink/gaze/breathing idle system, seven emotions, five gesture poses.

## Memory

She remembers what you ask her to (`remember that...`, `my name is...`,
`I love...`) in `localStorage` — up to 40 facts, shown as `MEM n`, wipeable
from the voice console.

## Running

Static site, no build, no keys, no cost. Open `index.html` or visit the live URL.
Chrome/Edge give the full voice loop; other browsers get typing + her voice.

- `?demo=1` — skip the boot screen
- `?selftest=1` — run the built-in 8-check self test
- `?pose=speaking&emotion=happy` — force a state (used for screenshot tests)
