 ________________       ________       ____________ 
|___   __________|    ,'  ____  `.    |___   ____  `.  TM
  ,' ,'              /  ,'    `.  \     ,' ,'    `.  \ 
 /  /               /  /        \  \   /  /        \  \ 
|  |               |  |          |  | |  |          |  |
|  |               |  |          |  | |  |          |  |         ___
|  |           __  |  |          |  | |  |          |  | _  _   /   |
|  |          |  | |  |          |  | |  |          |  || '` `./ /| |
 \  \        /  /   \  \        /  /   \  \        /  / | | | ||__  |
  \  `.____,'  /     \  `.____,'  /     \  `.____,'  /  | | | |   | |
   `.________,'       `.________,'       `.________,'   |_|_|_|   |_|


              l o c k j a w :   t h e   o v e r d o s e

                        m i l e s t o n e   4

             f o r    g a m e    b o y    a d v a n c e


LOCKJAW: The Overdose (formerly Tetanus On Drugs) is a tetromino
based game that simulates the the influence of hallucinogenic drugs.


=== System Requirements ===

For play on Game Boy Advance:
  Game Boy Advance system, GBA SP system, or GameCube Game Boy player
  Flash cartridge programmer, GBA Movie Player, or PC multiboot cable
For play on PC:
  x86 family processor clocked at 500 MHz or faster
  VisualBoyAdvance emulator
  Operating systems matching VBA's system requirements, such as
    Microsoft Windows 98 or ME
    Microsoft Windows 2000 or XP
    GNU/Linux with SDL and glibc 2.2
    BeOS


=== Building ===

If you are using only the tod.gba binary, skip this section.

You'll need to have two GCC toolchains installed: one MinGW toolchain
with the Allegro library (4.0 or later) installed, and one devkitARM
R18 toolchain.  To get these tools, visit these sites:

  http://www.mingw.org/
  http://alleg.sourceforge.net/
  http://www.devkitpro.org/

Currently, the makefile works only on Windows.  It has been tested
under Windows 2000 Professional.  You'll probably be able to get it
to work in GCC in Linux by changing slashes and editing some of the
batch files.

Building TOD is as easy as 1-2-3:

1. Start MSYS and 'cd' to the folder containing TOD source code.
2. Make sure that both .../devkitARM/bin and .../mingw/bin are
   in your PATH.
3. make

To create the header information necessary for using send tools
that do not automatically fix the cartridge header, you'll
need GBAFix by DarkFader, which is included in this package.
If your send tool fixes the cartridge header itself, you may
comment out the call to gbafix at the end of the makefile.

If you have the Info-ZIP tools (http://www.info-zip.org/) on
your path, you can create a zip file containing the source code
and the binary.  NOTE: If you add any files to the build, make
sure to list them in zip.in so that the script can pick them up.
To create a zip file named todgba.zip:

C:\...\tod> make zip


=== Installing ===

You can run TOD from within VisualBoyAdvance.  You can copy TOD
to a bare GBA flash cart.  You can use TOD in a GBA shell such as
PogoShell (http://www.obsession.se/pocket/) or the basic shell that
comes with some flash carts.

You can convert TOD to a multiboot ROM by renaming it to 'tod.mb'.
From there, you can use it in a multiboot menu such as the one
available at http://www.pineight.com/gba/.  You can use the MBV2
or XBOO cable to copy the program to the GBA's memory and run it.
(If you use the last option, you can keep TOD in the GBA's memory
by using the "Sleep" command in the pause menu instead of turning
off the GBA's power.)


=== Game Play ===

--- Title screen ---

Pad up, down: Change mode
A, Start: Start game

You can choose to play Marathon, 150 Dash, Time Trial, or Death Mode.
You can also choose to enter an options menu (which does not yet
exist in this milestone and will currently kick you right back to the
title screen), or restart the GBA system.

MARATHON:
  Play until you top out and die.
150 DASH:
  How fast can you score 15,000 points?
TIME TRIAL:
  How many points can you score in three minutes?
DEATH MODE:
  "Tod" is German for "death".  In this mode, pieces start out
  on the bottom as if you had pressed Up on the Control Pad, and
  you're given only a short time to slide them into place.  You may
  recognize this mode from a coin-op falling tetromino game pictured
  in the "Death 800" video floating around the Internet.


--- The game ---

Control Pad left, right, down: Move piece
  Pad up: Drop piece all the way
       B: Rotate piece anti-clockwise
       A: Rotate piece clockwise
  B+A, L: Swap piece with reserve piece
       R: Hold to zoom out
   Start: Pause/resume game

Pieces fall from the top of the playfield.  It's your job to move
and rotate those pieces such that they fall neatly into place in
complete, unbroken horizontal lines, which are removed from the
board.  The falling piece casts a shadow showing where it will fit.
If you press up to drop the piece, the piece moves all the way to
the bottom, but you can still slide it for a split second.  Learn
to smoothly press up then sideways (pretend it's a special move in
a Street Fighter type game) to quickly place pieces under other
pieces.  The added speed will give you an edge in 150 Dash and
Time Trial.

After a line is removed from the board, everything above it falls
down one or more rows.  Unlike older falling block games, where the
blocks always moved down exactly one space per cleared line, TOD uses
a smarter gravity engine that moves each contiguous mass of blocks
down until it lands on something.  This allows for chain reactions.


--- Scoring ---

Normally, each line is worth 100 points, but if you     Lines  Score
make at least four lines with one piece, you earn         1      100
even more points.  (Mathematicians will note that         2      200
the scoring system follows a Fibonacci sequence.)         3      300
Chain reactions can involve 10 or more lines at once      4      500
and will increase your score immensely.                   5      800
                                                          6     1300
If you make a 4x4 block square out of four entire         7     2100
pieces, it becomes a solid silver square.  Part of        8     3400
a silver square in a line gives you 500 points; part      9     5500
of a gold square produces 1,000 points.  Because         10     8900
broken pieces (that is, pieces partially removed as
part of a horizontal line) can't make squares, TOD helps
you by marking broken pieces as darkened single blocks.

Death Mode scoring is different.  At this time, I have not made a
final decision on its scoring system.

If you rotate a piece into a tight space to complete a line, the
screen breaks up into individual blocks, which fall.  Perform this
move to reduce your stack, but note that it will destroy any silver
or gold squares, so do it only if you are in deep trouble.

Your opponents are:
 o time.  The pieces will pile up on you if you don't think fast,
   ESPECIALLY in Death Mode.
 o hallucinogen simulation.  The screen will begin to distort
   in various ways.  Once the drug dosage begins to increase,
   you start to lose track of what's happening in the playfield.


--- The pause menu ---

Pause menu controls:
Start: Resume game
Pad: Move
A: Select

In the pause menu, you can change the wallpaper displayed behind the
playfield, read the help file, put the GBA to sleep (which is like
turning it off but keeps the program in memory), or quit the game.


--- Tips ---

To learn how to play falling tetromino games, visit
http://tetrisconcept.com/

To learn how to make silver and gold squares, visit
http://everything2.com/?node=four-column+Tetris+strategy
http://fortes.com/projects/blockmaker/

To optimize the performance in VisualBoyAdvance, set the screen
size to 1x, set the frame skip to 1, and don't use a BIOS file.
With these settings, I was able to achieve 100% on a 333 MHz
Pentium II laptop.

The game will be playable on some of the other popular emulators
(Boycott Advance and BatGBA), but Boycott Advance will delay
sampled sound more than the GB's tone generators, causing music
to fall horribly out of sync, and BatGBA doesn't even emulate the
tone generators at all.  NO$GBA does not show the playfield.
It does not work at all on Mappy VM or any other emulator not
accurate enough to run commercial ROMs.  Use VBA if you're not
using GBA hardware.


=== Technical Information ===

The change log is in CHANGES.txt


=== Known Issues ===

If you leave the game running (presumably on mains power) for more
than a year straight, it may crash because the number of retraces
since power-on will have increased beyond 2^31.

There is no attract-mode demo.

There isn't another song.

The technical workings of the program are not yet well documented.

The game looks somewhat washed out on GBA systems modified with an
Afterburner internal light.  It looks OK on Game Boy Advance SP
and Nintendo DS systems, which use an internal light.

The makefile works only on Windows.  It does not work out of the box
in Linux systems because of linefeed and slash issues.  I currently
have no Linux partition to test with; patches are welcome.


=== Questions and Answers ===

Q: Why can't I hear bass?

You're using the tiny internal speaker of the GBA system, which
has little or no response below 500 Hz.  Use headphones.

Q: Why do the game's controls feel so much crisper on hardware
than on the emulator?

Because TOD's hallucinogenic simulation impairs your vision of
the playfield, your brain adapts by using the sound of the game.
Emulators tend to delay sound with respect to graphics (on my
machine, VBA delays sound by 200 ms!), making TOD feel laggy.
(It's the same thing that makes rhythm games such as Dance Dance
Revolution for GBC and Britney's Dance Beat by THQ unplayable in
emulators.) In addition, TOD runs at a solid 60 frames per second
on GBA hardware, but VBA comes set up out of the box to skip
rendering every other frame because it works better that way for
most games on slow hardware.

Q: Why does your game's music sound so familiar?

To some listeners, the game music sounds like "It's All About the
Benjamins" by Puff Daddy and the Foo Fighters; to others, it's
"I Don't Like the Drugs" by Marilyn Manson.  The song was written
as a comment on how Manson copied Puffy.  No, the repeated Morse
"DLI" over the end of the song doesn't stand for anything.

The "win" music in 150 Dash and Time Trial modes is my
arrangement of "Trepak" from Nutcracker Suite composed by
Peter Tchaikovsky.  This song was also used as the "win" music
in Nintendo's Tetris(R) falling tetramino game for Game Boy.
All of Tchaikovsky's works have fallen into public domain in
the United States and the European Union.

Q: Why does the build process require the Allegro library?

The Allegro library includes a portable implementation of a
graphics canvas and a bitmap loader.  This way, I don't have to
deal with all the intricacies of bitmap loading myself.

I used Allegro instead of SDL because SDL doesn't have built-in
graphics primitives and because building Allegro on MinGW is
much easier than building SDL on MinGW.  But most importantly,
I used Allegro because I was familiar with it.  I had started
graphics programming on PCs in 1997 using MS-DOS, before I had
ever owned a Windows 9x system (my first was in July 1999), and
unlike Allegro, SDL never had a version that targeted MS-DOS.

Q: Why don't you implement Game Link support?

No publicly available GBA emulator supports Game Link.  I didn't
even have a second GBA to test it on until the day before TOD M3
went gold.


=== Legal Information ===

--- Manual copyright ---

TOD User Manual
Copyright (C) 2002-2003 Damian Yerrick
This manual (but not the accompanying programs) is subject to the
QING PUBLIC LICENCE

Copying, distribution, public performance, public display, digital
audio transmission, and use of this work is permitted without
restriction.  Circumvention of any technological measure or measures
which effectively control access to this work is permitted without
restriction.  Preparation of derivative works is permitted provided
that you cause any such work to be licensed as a whole at no charge
to all third parties under the terms of this License.

--- Software copyright ---

TOD for Game Boy Advance:  falling tetramino game
Copyright (C) 2000-2003 Damian Yerrick
                        <http://www.pineight.com/>

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program, in the file COPYING; if not, write to
  Free Software Foundation, Inc.,
  59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.

Special licenses for commercial and other applications which
are not willing to accept the GNU General Public License
are available by contacting the author.

The standard electronic distribution of this program contains
source code for the executable portion of the program but not
the much larger source code for the video and sound assets.
To receive a CD containing the full source code of this program,
send a U.S.-negotiable money order for USD $10 to
  Damian Yerrick
  730 Runnion Avenue, Fort Wayne, IN 46808-3744, USA.

--- Trademarks ---

Pin Eight, LOCKJAW, the LOCKJAW logo, TOD, the TOD logo, and
Tetanus On Drugs are trademarks of Damian Yerrick.  Nintendo,
Game Boy, and GameCube are trademarks of Nintendo.  Tetris is a
trademark of The Tetris Company.  Microsoft Windows is a trademark
of Microsoft Corporation.  Pentium is a trademark of Intel
Corporation.  GNU is a trademark of Free Software Foundation Inc.
Linux is a trademark of Linus Torvalds. Be is a trademark of the
company that bought the assets of Be Inc.  Dance Dance Revolution
is a trademark of Konami.  Street Fighter is a trademark of Capcom.
Afterburner is a trademark of Triton Labs.  Britney's Dance Beat
is a trademark of Britney Brands Inc., licensed to THQ Inc.

This product is not sponsored or endorsed by Nintendo.  It displays
a Nintendo logo during startup pursuant to Sega v. Accolade.

This product is not sponsored or endorsed by The Tetris Company.