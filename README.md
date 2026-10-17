# Win Mancala — Capture + Avalanche

Both game modes are included in this delivery. Capture is the default. Choose Game mode above the board to switch to Avalanche. The original vertical board and colors are retained, with responsive controls for phones, tablets and desktops.

## Open either version directly

- index.html: combined app, starting in Capture mode.
- capture.html: direct entry to Capture mode.
- avalanche.html: direct entry to Avalanche mode.
- You can also append ?mode=capture or ?mode=avalanche to index.html on the published site.

Both direct pages include the selector so the customer can reach either game without replacing files or publishing a second repository. They share the same engine, styles and images. All three pages should be uploaded together.

## Use

1. Select the mode used in your GamePigeon game.
2. Copy all 12 pit counts and both scores, including zeros. My pits are the LEFT column; opponent pits are the RIGHT column. Both columns are numbered 1–6 from TOP to BOTTOM. Opponent store is on top, My store below.
3. Select My turn and press Find Best Move. Play the blue outlined pit in the indicated column. Opponent's turn is optional and predicts their strongest move.
4. Update the board after each real move and search again. An extra turn keeps the same player.

Changing mode keeps entered counts, cancels the active search, clears the old suggestion and updates the rules text. Ensure the counts match your current game. Reset / Clear empties the pits and zeros both scores without changing the chosen mode. Load example supplies a nonuniform sample board, not the customer's current game.

## Separate rules

Capture: Sow once around the ring as needed, skipping the opponent's store. A last stone in your store grants an extra turn. A last stone in a previously empty own pit captures that stone and the occupied opposite pit. There are no relay pickups.

Avalanche: Sow while skipping the opponent's store. When the last stone lands in a pit that now has more than one stone, pick up all of that pit and continue, on either side. A last stone in your store gives another turn; a last stone in an empty pit ends the move. There is no opposite-pit capture. Game end is checked after the complete chain.

In both implemented modes, an empty side at the end of a move ends the game and remaining stones go to their owner's store. Randomized counts are accepted without requiring a total of 48.

## Strategy and limits

The search considers future moves and both players' replies. Prefer a close win chooses the smallest positive minimax margin among the current first-move choices only when all are solved to game end. Otherwise it uses the strongest estimated move. Strongest winning margin always maximizes My score advantage. Opponent's turn always favors their strongest play.

Actual opponent choices and later close-win choices can change the final margin. A win or exact narrow margin cannot be guaranteed from every position. Search runs in a background worker with a 1, 3 or 10-second limit and depth cap of 64. Depth-aware cache entries distinguish bounds from exact values. Tables are scoped to one search and keys include the game mode. Unsolved results are clearly labeled as estimates.

## GitHub Pages deployment

Extract the ZIP and upload ALL its contents to the repository root, including index.html, capture.html, avalanche.html, main.js, style.css and the images. Enable Settings → Pages → Deploy from a branch → main → / (root). The customer can use the site homepage or the capture.html and avalanche.html URLs directly. No backend, API key or build is needed.

For local use, serve the folder over HTTP. Opening HTML directly as a file may block workers. The site has been tested in a desktop browser at mobile and desktop viewport sizes, not on a physical iPhone or a live deployment. Original artwork and attribution are preserved.

This is the combined replacement package. Previous standalone Capture and Avalanche deliverables were not overwritten. See TEST-REPORT.txt for checks performed on this combined app.
