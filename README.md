# Minesweeper
The Minesweeper game in 100 lines of JavaScript


https://i.imgur.com/nOr6M7t.png
We will create three arrays:
1. "board", which will contain: 'mine' for mine or a number 0 thru 8 which is the number of mines in the eight neighboring tiles.
2. "tile", which will consist of dynamically created image (IMG) objects, on which the player will click. The image can be:

0.png thru 8.png - number of mines in neighboring tiles (blank means zero)

hidden.png - covered tile

flag.png - flag

question.png - question mark

These two are only shown after the game is finished:

mine.png - a mine

misplaced.png - a place where a flag was incorrectly placed



3. "picture", which will contain on of the following strings: hidden, flag and question so that we don't have to get the image name and strip the '.png' ending each time we need to check what the tile is showing

Because JavaScript does not directly support two-dimensional arrays, we will create an array of arrays (lines 13-19). For example the main array 'board' will consist of 5 elements representing rows of the matrix. Each of those elements will also be an array, whose elements represent an actual tile.

First, in the 'init' function, we'll create the tiles and place them on then screen. Then we'll randomly place the mines.
When the player left clicks on a covered tile, we'll reveal its contents. If the value of the tile equals zero (which means none of the neighboring tiles have a mine), we'll also reveal all the surrounding tiles. If any of the surrounding tiles' value is zero, we'll reveal the tiles surrounding that tile... And so on and so on... The function 'reveal' will call itself recursively, until all the neighboring zero tiles are revealed. That's probably the most interesting part of this code.

The game ends when the player clicks on a tile that contains a mine (lose) or all non-mine tiles are revealed (win). In either case we display all the mines.
