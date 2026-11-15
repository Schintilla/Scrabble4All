# Scrabble4All

A browser-based word board game, inspired by the old Windows "ScrabOut" game.
Plain HTML, CSS and JavaScript: no build step, no dependencies.

*Not affiliated with or endorsed by the makers of Scrabble.*

## Files

```
index.html                              the game
scrabble4all-default-dictionary.txt     default word list (one word per line)
scrabble4all-custom-dictionary.txt      optional: your own list, loaded automatically
sounds/                                 Tiledown.wav, Slide.wav, Shuffle.wav, Winner.wav, Error.wav
```

The word list and sounds are loaded when the page starts, so keep these files
together. Edit the `.txt` files to change the dictionary; no code change needed.

## Run it

- **Online:** deploy the repository to any static host (Vercel, GitHub Pages, ...).
- **Locally:** serve the folder, for example `python -m http.server`, then open
  `http://localhost:8000/`.
- **Straight from disk:** browsers block a page from reading neighbouring files,
  so the game asks you to choose `scrabble4all-default-dictionary.txt` once per
  visit. Sounds still work.

Works best in Microsoft Edge or Google Chrome. Other browsers play fine, but
saving files falls back to a normal download.

## Features

- 15×15 board, standard tile set and premium squares, 2–4 players
- Computer opponent with **Easy / Medium / Hard** levels, changeable mid-game
- Reject the computer's last move and make it try again
- Drag tiles within the rack, onto the board, between squares, or back to the rack
- Swap tiles, swap all, shuffle, recall; sound effects (toggle in Options)
- Look up a word's meaning (double-click a word in the score list; needs internet)
- **Save / open games** to resume later (Game menu)
- Customisable dictionary (Dictionary menu): add or remove words, load a new
  list, save it, restore the default

## How to play

1. Choose the number of players and tick **Computer** for any computer player.
2. Click a rack tile, then a square (or drag it there). Click a placed tile to
   take it back. A blank tile asks which letter it stands for.
3. Press **Done** to play your word, or **Pass** / **Swap tiles**.
4. The game ends when the bag and a rack are empty, or after everyone passes
   twice in a row. Remaining tile values are deducted.

With more than one human player, everyone shares the same screen and a
"your turn" box hides the rack between turns.

## Dictionary

At start-up the game loads `scrabble4all-default-dictionary.txt`. If
`scrabble4all-custom-dictionary.txt` is also present it replaces the default.
**Dictionary → New dictionary…** loads any plain-text word list, and **Save**
writes your changes to a file on your own computer (the hosted copy is not
modified; commit the updated `.txt` to the repository to publish it).
**Restore default** goes back to the default list.

## Saved games

**Game → Save game** writes a `.json` file with the board, racks, bag, scores
and settings. **Game → Open game…** resumes it. A saved game does not include
the dictionary, and it contains every player's rack.
