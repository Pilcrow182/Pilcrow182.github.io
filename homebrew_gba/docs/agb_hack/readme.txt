AGB_Hack version 1.6
Copyright (C) 2007 by Donnie Russell



AGB_Hack is based on RevivedHack 1.1,
an adaptation of Don G. Kneller's
PC Hack 3.61.

Level compression uses Markus Franz
Xaver Johannes Oberhumer's
miniLZO 1.08, a mini subset of the LZO
real-time data compression library.



History Of This Game
====================

[1984?] Hack by Jay Fenlason with help from Kenny Woodland, Mike Thome and Jon
        Payne.

       Inspired by Rogue, with twice as many monster types.

[1985] Hack 1.0.3 by Andries E. Brouwer.

       Evolution of Jay Fenlason's Hack, more than three times larger.

[1986] PC Hack 3.61 by Don G. Kneller.

       Hack 1.0.3 ported to MS-DOS, with new features and bugfixes.

[1987] NetHack project begins, organized by Mike Stephenson.

[2004] RevivedHack 1.1 by Donnie Russell.

       PC Hack 3.61 updated for modern operating systems, with color, sound
       effects, and bugfixes.

[2007] AGB_Hack 1.6 by Donnie Russell.

       RevivedHack 1.1 ported to the GameBoy Advance, with level compression,
       menus, graphical tiles, and bugfixes.



License
=======

The software contained in this archive is freeware, and may not be sold in any
form for any reason whatsoever. This software is provided to the end-user
"as is", and comes with no warranty of any kind. In no event shall the
copyright owner be liable for any damage that may result from the use of this
software.

This software may be redistributed provided that the original archive is
whole, intact, and unmodified. Only copies identical to the original
distribution archive available from my web site are authorized for
redistribution. Proper credit must be given to all people involved in the
creation of this software near the point of redistribution. Redistribution of
this software on cartridge media is strictly prohibited.



Getting Started
===============

When the initial screen appears the game will ask you to enter your name. You
can allow the game to pick a name for you by pressing the START button (Enter
key), or you can enter one with the key selector. Turn it on by pressing the L
button, then type your name by moving the cursor around the alphabet with the
directional buttons, pressing the B button on each letter. Press the L button
to turn the selector off. When the selector is off, pressing the B button
(Backspace key) moves the cursor back one space. Press the START button to
enter your name.

At this point, the game will seed a sequence of random numbers based on the
amount of time elapsed since startup. Hack's gameplay is influenced by the
year, day of the year, and time of day, which are set to random values in the
GameBoy Advance version.

Next, you can select the type of character you would like to play, or have one
chosen for you randomly. Move the arrow-shaped cursor using the directional
buttons to the character you want then press the Enter, B, or A button. Each
character has its own strengths and weaknesses, so choose carefully.

Use the directional buttons to move your character. To move diagonally, hold
down the SELECT button, select the direction, then release the SELECT button.
To run, hold down the START button, select the direction, then release the
START button. You can also release the SELECT/START button before releasing
the directional buttons.

Roguelike games such as Hack are typically played by entering commands with
a keyboard. Since the GameBoy Advance doesn't have a keyboard, two alternative
input methods are available.

The easiest method is to press the Start button (Enter key) to open the game
menu, which consists of two screens, for objects and actions. Press the Left
and Right directional buttons to switch between them. Objects listed on the
object menu are those which you are currently carrying. Selecting an object on
this menu brings up a list of things you can do with that object. Some actions
on the actions menu also work on objects, either in your inventory or on the
ground. Pressing the R button (Escape key) exits the menu.

The second method is more cumbersome but also more flexible. Commands can be
entered by "typing" them with the key selector. Consult the two in-game help
screens that list the available commands (accessed with the '?' command), and
the meaning of various symbols (the '/' command) for more information.

While playing, some game messages are too numerous to be displayed at once. To
continue viewing the following message(s), press the A button (Space key).

To cancel a command in progress, press the R button (Escape key).

Entering the '@' command with the key selector toggles the automatic picking
up of objects on or off. This setting is off by default. Gold is always picked
up if it is the only object at your current location.

To repeat the last command (for example, to fire another arrow), open the key
selector with the L button, move the cursor to the 'a' key (the "again"
command) and press the R button. Thereafter, pressing L then R repeatedly will
continue entering the same command.

At the bottom of the display, you can see what dungeon level you are on, how
many hit points you have now and will have when fully recovered, how much gold
you are carrying, what your armor class is (the lower the better), your
strength, experience level and the state of your stomach. Please note that in
graphical tile mode some status information may be obscured by the minimap.

If you ever find yourself inside a room with no exits, use the 's' (search)
command repeatedly along the walls of the room. This command can also be used
to find hidden traps. By default, the Select button is defined as 's'.

To quit the current game, enter the 'Q' command with the key selector, or
select "Quit" from the actions menu screen.



How Saved Games Work
====================

As you play AGB_Hack, each "keystroke" is recorded in a special area of memory
that is not erased when the power is turned off. Before ending a game session,
you should enter the command 'S' with the key selector to save and halt the
game, making it safe to turn off the power. If you accidentally turn off the
power without using this command first, there is a small chance that the saved
data will be corrupted.

To continue a previous game, turn on the console, and if a saved game is
found it will be played back to the point where you left off. During playback
a progress bar is displayed. Pressing and releasing the A button allows you to
switch the progress bar off so you can see each move being played. Holding
down the B button slows down each move. Saved games play back faster with the
progress bar turned on.



A Note About Memory
===================

There is a limited amount of memory available for saving games, enough
for 65,523 "keystrokes". Any input made after this limit is not recorded, but
the game will continue playing normally. In my own experience, this limit has
never been reached, even for winning games.

Also, in testing, I have found that the GameBoy Advance has enough memory to
store around 30 visited dungeon levels, which theoretically is enough for a
complete winning game. Levels are compressed when not in use, and since the
amount of compression varies with each level, this is a very rough estimate.

If you attempt to visit more than 30 levels, there is an increasing chance
that the game will run out of memory. When that happens the dungeon will
collapse, immediately ending the current game. However, you will still be able
to see your final score.

Addendum:

I made adjustments to memory usage in version 1.6 that may lower the risk of
dungeon collapses, even after visiting 35 levels.



Controls
========


Buttons (key selector off)
--------------------------

A        Type Space key

B        Type Backspace key

L        Turn key selector on

R        Type Escape key (cancel command, close menu)

START    Type Enter key (open game menu when game is waiting for a command)
         When used with directional buttons: run in specified direction

SELECT   Type defined key, initially 's' (search command)
         When used with directional buttons: move in specified diagonal
         direction.


Buttons (key selector on)
-------------------------

A        Type Space key, keep key selector on

B        Type selected key, keep key selector on

L        Turn key selector off

R        Type selected key, turn key selector off

START    Type Enter key, turn key selector off

SELECT   Define selected key, initially 's' (search command)
