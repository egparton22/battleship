# Bug Report: Battleship

**Game:** https://egparton22.github.io/battleship/

## How I tested
- **Automated play:** a script played 36 full games against all three computer levels (Easy, Normal, Hard). It checked that every game ended correctly and that the computer never fired at the same square twice.
- **Stress tests:** clicking fast, restarting in the middle of a game, and starting a new game right after one ended.
- **Screen sizes:** a laptop browser plus phone-sized screens (iPhone SE and smaller).

## Bugs found and fixed

### 1. The computer got a free shot after a restart
- **What happened:** If you fired and then clicked **New game** while the computer was still "aiming," its leftover shot landed in your *next* game. That meant the computer fired before you, even though you're supposed to go first.
- **Why:** The computer waits about half a second before each shot, so it feels like a real opponent. Restarting didn't cancel a shot that was already waiting.
- **Fix:** Each game now gets its own ID number. A delayed shot only counts if it belongs to the game that's still being played.

### 2. The "You win / You lost" pop-up showed up in the new game
- **What happened:** If you clicked **New game** right after a game ended, the result pop-up from the old game appeared on top of the new game's setup screen.
- **Why:** Same cause as bug 1. The pop-up appears after a short delay, and starting a new game didn't cancel it.
- **Fix:** The same game ID check. The pop-up only appears if that game is still the one on screen.

### 3. Row and column labels didn't line up with the squares
- **What happened:** The numbers 1–10 and letters A–J slowly drifted out of line with the board. By row 10 and column J, the label sat noticeably off its square, which makes calling a shot like "J10" confusing.
- **Why:** The board has small gaps between squares, but the labels didn't include those gaps.
- **Fix:** The labels now use the same spacing as the squares.

### 4. The score line broke apart on phones
- **What happened:** The line "Computer shots / Hits / Accuracy" split into scattered pieces on small screens, with the numbers separated from their labels.
- **Why:** The layout treated each word and number as a separate block and spread them apart.
- **Fix:** The score line now flows as one normal sentence and wraps neatly.

## Checks that passed (no bug found)
- You can't fire at the same square twice, or fire while it's the computer's turn.
- Ships can't overlap or hang off the edge of the board.
- Wins and losses are detected correctly. When you lose, the enemy's remaining ships are revealed.
- The computer plays fair. It never looks at your ships, only at its own hits and misses.
- The Hard level beats Normal: about 47 shots to sink a fleet vs. about 52 on Normal (random guessing takes 90+).
