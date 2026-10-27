# Battleship: You vs. the Computer

A browser version of the classic Battleship board game, played against a computer opponent.

**Play it here:** https://egparton22.github.io/battleship/

## How to play
1. Place your 5 ships (or click **Place ships randomly**). Press **R** or click **Rotate** to switch direction.
2. Pick the computer's skill level and click **Start battle**.
3. Click squares in **Enemy Waters** to fire. Red X = hit, white dot = miss. The computer fires back after each shot.
4. Sink all 5 enemy ships first to win.

## The computer opponent (3 levels)
- **Easy:** fires at random squares.
- **Normal:** searches in a checkerboard pattern, and once it hits a ship it attacks the squares around it until the ship sinks.
- **Hard:** before every shot it counts all the ways your remaining ships could still fit on the board and fires at the square most likely to hold a ship.

The computer plays fair: it never looks at where your ships are. It only knows its own hits, misses, and which ship it sank.

## How it's built
One file, `index.html` (HTML for the page, CSS for the look, JavaScript for the game rules and the computer opponent). No servers, accounts, or installs. It's hosted free on GitHub Pages.
