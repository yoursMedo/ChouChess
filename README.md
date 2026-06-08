# Chou Chess

Dedicated to meri jaan.

Built on top of [0xBitBuster/python-chess-engine](https://github.com/0xBitBuster/python-chess-engine). Audio samples sourced from [gleitz/midi-js-soundfonts](https://github.com/gleitz/midi-js-soundfonts) and processed with a custom reverb algorithm not included in this package.

---

## Getting started

```bash
git clone https://github.com/yourusername/chill-chess.git
cd chill-chess
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 ChessMain.py
```
---

## How it works

Each move triggers a music box note. A pointer starts at C4 in the following array of natural notes:

```
A3  B3  C4  D4  E4  F4  G4  A4  B4  C5  D5  E5  F5  G5
```

When white moves a piece, the pointer shifts right by the Manhattan distance of that move. When black moves, the pointer shifts left by the same measure. The array wraps at both ends. The note at the new pointer position is played on its own mixer channel — white and black have separate channels so their notes never interrupt each other. A birdsong recording loops softly in the background throughout the game.

---