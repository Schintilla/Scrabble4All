# ScrabOut

A single-file, browser-based word board game in the style of the old Windows
"ScrabOut" Scrabble game. No install, no server, no dependencies: open
`ScrabOut.html` (or `index.html`) in a modern browser and play.

*Not affiliated with or endorsed by the makers of Scrabble.*

## Run it

- **Locally:** download the file and double-click it.
- **Online:** enable GitHub Pages (Settings → Pages → deploy from `main`, root).
  If the file is named `index.html`, the game is served at
  `https://<your-name>.github.io/<repo>/`.

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
- Large built-in dictionary you can customise (Dictionary menu):
  add or remove words, load a new list, save it, restore the default

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

The default word list is embedded in the HTML file. Any plain-text file with
one word per line can be loaded with **Dictionary → New dictionary…**.
If `ScrabOut-dictionary.txt` sits next to the page and it is served over
http(s), it is loaded automatically. In Edge/Chrome the game also remembers the
dictionary file you last saved or opened and offers to load it next time.

## Saved games

**Game → Save game** writes a `.json` file with the board, racks, bag, scores
and settings. **Game → Open game…** resumes it. A saved game does not include
the dictionary, and it contains every player's rack.
