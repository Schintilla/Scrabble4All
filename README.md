# Scrabble4All

A browser-based word board game, inspired by the old Windows "ScrabOut" game.
Plain HTML, CSS and JavaScript: no build step, no dependencies.

*Not affiliated with or endorsed by the makers of Scrabble.*

## Files

```
index.html                              the game
UK-common-words.txt                     built-in dictionary (the default)
Collins-Scrabble Dictionary.txt         built-in dictionary
US-google-10000-common-words.txt        built-in dictionary
sounds/                                 Tiledown.wav, Slide.wav, Shuffle.wav, Winner.wav, Error.wav
```

The dictionaries and sounds are loaded when the page starts, so keep these files
together in the same folder. Each dictionary is a plain-text file with one word
per line (words of 2–15 letters, A–Z, any case; only the first word on a line is
used).

## Run it

- **Online:** deploy the repository to any static host (Vercel, GitHub Pages, ...).
- **Locally:** serve the folder, for example `python -m http.server`, then open
  `http://localhost:8000/`.
- **Straight from disk:** browsers block a page from reading neighbouring files,
  so the game asks you to choose `UK-common-words.txt` once per visit. Sounds
  still work.

Works best in Microsoft Edge or Google Chrome. Other browsers play fine, but
saving files falls back to a normal download.

## Features

- 15×15 board, standard tile set and premium squares, 2–4 players
- Computer opponent with **Easy / Medium / Hard** levels, changeable mid-game
- Reject the computer's last move and make it try again
- Drag tiles within the rack, onto the board, between squares, or back to the rack
- Swap tiles, swap all, shuffle, recall; sound effects (toggle in Options)
- Look up a word's meaning (double-click a word in the score list, or use
  **Check definition** in the Add word window; needs internet)
- **Save / open games** to resume later (Game menu)
- Choice of **four dictionaries**, switchable at any time (Dictionary menu):
  UK common words (default), Collins Scrabble Dictionary, US Google 10,000
  common words, or your own custom file
- Edit the dictionary: add or remove words, save it, restore the original list

## How to play

1. Choose the number of players and tick **Computer** for any computer player.
2. Click a rack tile, then a square (or drag it there). Click a placed tile to
   take it back. A blank tile asks which letter it stands for.
3. Press **Done** to play your word, or **Pass** / **Swap tiles**.
4. The game ends when the bag and a rack are empty, or after everyone passes
   twice in a row. Remaining tile values are deducted.

With more than one human player, everyone shares the same screen and a
"your turn" box hides the rack between turns.

## Dictionaries

Choose from the **Dictionary** menu at any time, even mid-game. The change
applies to the next word checked and to the computer's next move.

| Choice | File | Notes |
|---|---|---|
| UK common words | `UK-common-words.txt` | default |
| Collins Scrabble Dictionary | `Collins-Scrabble Dictionary.txt` | |
| US Google 10,000 common words | `US-google-10000-common-words.txt` | |
| Custom dictionary… | any `.txt` on your computer | browse to it; stays local |

A custom dictionary is never uploaded: the player browses to a file on their own
computer. **Save** overwrites that file (Edge/Chrome); **Save As…** writes a new
one. Amending a built-in list (**Add word**, **Remove word**) and saving turns it
into a custom file. **Restore default** reloads the selected built-in list (or
the UK list if a custom one is in use). Switching dictionary discards unsaved
amendments, with a warning first.

## Word meanings

Definitions come from the free [Free Dictionary API](https://dictionaryapi.dev/)
(`api.dictionaryapi.dev`), queried from the player's browser when they ask for a
meaning. Only the word being looked up is sent. The service is community-run, so
it can be slow or missing a word; the game then shows a link to Wiktionary.

## Saved games

**Game → Save game** writes a `.json` file with the board, racks, bag, scores
and settings. **Game → Open game…** resumes it. A saved game does not include
the dictionary, and it contains every player's rack.
