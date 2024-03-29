ZSNES v1.51 Documentation

================================
    N a v i g a t i o n
================================

    * NSRT Guide:    [http://zsnes-docs.sf.net/nsrt]

    * ZSNES Home Page:  [ZSNES.com]


================================================================================
~                                  G a m e s
================================================================================

............................................................
  1.                        ROMS
............................................................

** ROMs are not included with ZSNES!!! ** You must find them on your own.

Please read Wikipedia's article on ROM Images for a general overview.
[http://en.wikipedia.org/wiki/ROM_image]

In relation to SNES emulation, a "ROM image" is a computer file which is an
exact copy of the data that is contained in a 'R'ead 'O'nly 'M'emory chip inside
a game cartridge. This file contains the same data that a real SNES console
reads from the game cartridge. An SNES emulator loads this ROM into its own
memory, very much like how a real SNES operates.

A problem appears when you have a ROM image that is not an exact copy of the
data on a real SNES cartridge. Many of the ROMs available for download on the
Internet are not in fact exact copies of real SNES games. There are a variety of
reasons why a ROM that appears to be a real game is not an exact copy of the
cartridge data. For example, the ROM may have been incorrectly "dumped" from the
cartridge, which can introduce errors. Certain prolific ROM "releasers" will
"hack" a ROM to include an introduction that advertises the releaser. Regardless
of the reason for an imperfect ROM image, these "bad" ROMs can display errors
when they are played in an emulator.

Emulator developers generally try to make their emulators work with "good" ROMs;
that is, ROMs that are perfect copies of the data on a real game cartridge. The
developers of ZSNES in particular are unable to provide any help to people who
are using "bad" ROMs. You must use a good ROM if you want any chance of playing
an error-free game.

We recommend using NSRT to verify that your ROMs are "good" dumps. In some
cases, NSRT can actually modify a "bad" ROM in such a way that it becomes a
"good" ROM. Please read the documentation included with NSRT for additional
information. [http://nsrt.edgeemu.com]


............................................................
  2.                   Compatibility
............................................................

There are many reasons why a particular ROM may not work correctly with ZSNES.
Here is a list of things you can do to improve your chances of a ROM working
with ZSNES:

  * Make sure your ROM is actually a "good dump." Often a ROM appears to be from
    a particular game/cartridge, but it *is not* in fact a perfect copy of the
    data on that cartridge. You can use NSRT to scan your ROM and tell you if it
    is a good dump. In some cases, NSRT can actually modify a "bad" ROM in such
    a way that it becomes a "good" ROM.
  * Your ROM may be a game that uses the SuperFX special chip. It may also be
    "interleaved." ZSNES cannot detect when a ROM is interleaved with the
    SuperFX interleave method. There is more information about this below, in
    the Special-Chip Games section under SuperFX. In cases where ZSNES cannot
    detect a ROM's interleave method, ZSNES will incorrectly report the ROM as
    -not- interleaved, and the ROM will fail to load.
  * If you have turned off sound, you should re-enable it. If you wish to mute
    the sound output, simply move the volume slider to 0%. Many games require
    sound emulation to be active in order to work correctly, so disabling sound
    can "break" a lot of games.
  * If you have changed the percentage of execution in the ZSNES configuration
    file, change it back to 100. However, there are a few particular games that
    may work better if the percentage to execute is set to either 120% or 80%.

The developers of ZSNES make no guarantee that any particular game will work.
While we wish to play these incompatible games as much as you do, sometimes it
is just not possible. Furthermore, ZSNES is in a constant state of development.
Compatibility with a particular game may change between releases of ZSNES.

In the past, ZSNES developers programmed the emulator to "hack" certain games.
These "hacks" would modify in-memory certain incompatible games, to get them to
work with ZSNES. Some hacks were also used make certain games run at full speed
if they were too slow. Sometimes, however, a particular game hack will break
other parts of accurate SNES emulation.

As the emulation accuracy of ZSNES has improved, these hacks have become less
necessary. In general, game hacks are removed whenever possible. With the
current state of emulation in ZSNES, no new game hacks will be added.

In conclusion, if you have tried the steps above, and your game still doesn't
work, *we're sorry*; however there is nothing we can do. ZSNES is developed for
*emulation accuracy*, with game compatibility as a side effect, *not* the other
way around. The most you can do is try another emulator or hope that ZSNES will
become accurate enough to be able to run your particular game.


............................................................
  3.                 Special-Chip Games
............................................................

The NSRT SNES Add-on Chip information article was frequently referenced for the
information assembled on this page. [http://nsrt.edgeemu.com/INFO/chipinfo.htm]

You may find that the section on Enhancement chips in the Super Nintendo article
at Wikipedia contains some interesting historical information, not covered in
this FAQ. [http://en.wikipedia.org/wiki/Super_Nintendo_Entertainment_System]

A number of games developed for the Super Nintendo included additional
special-purpose processors on the game cartridge. A game would use this special
processor to accomplish something that wasn't possible using just the standard
SNES hardware. It is impossible to represent these processors with ROM data; in
order for these games to work, ZSNES must emulate these special processors, in
addition to all the standard SNES hardware (which ZSNES already emulates).

Below is a list of all known special processors, followed by a list of the games
known to use each processor.

 - - - -
   C4
 - - - -
  The C4 chip is a math co-processor with limited graphical processing
  capabilities.

     * Megaman X 2 (USA) / Rockman X 2 (Japan)
     * Megaman X 3 (USA, Europe) / Rockman X 3 (Japan)

 - - - - - - - -
  Nintendo DSP
 - - - - - - - -
  Each of the Nintendo DSP chips have identical hardware, but different software
  (firmware).

     + DSP-1 (supported)
         * Ace wo Nerae!
         * Armored Trooper Votoms
         * Ballz 3D / 3 Jigen Kakutou Ballz
         * Battle Racers
         * Drift King Shutokou Battle '94
         * Drift King Shutokou Battle 2
         * Final Stretch
         * Hashiriya Kon
         * Korean League
         * Lock On
         * Michael Andretti's Indy Car Challenge
         * Pilotwings
         * Super 3D Baseball
         * Super Air Diver
         * Super Air Diver 2
         * Super Bases Loaded II
         * Super F1 Circus Gaiden
         * Super Mario Kart
         * Suzuka 8 Hours
     + DSP-2 (supported)
         * Dungeon Master
     + DSP-3 (partially supported)
         * SD Gundam GX
     + DSP-4 (supported)
         * Top Gear 3000 (USA) / Planets Champ TG 3000 (Japan)

 - - - -
  OBC1
 - - - -
     * Metal Combat

 - - - -
  SA-1
 - - - -
  The SA-1 is a 65816 chip, although at a higher clock then the SNES's
  internal one. [Quoted from http://nsrt.edgeemu.com/INFO/chipinfo.htm]

     * Asahi Shinbun Rensai - Katou Ichi-Ni-San Kudan Shougi Shingiru
     * Daisenryaku Expert WWII
     * Derby Jockey 2
     * Dragon Ball Z - Hyper Dimension
     * Hanyuu Meijin no Omoshiro Shougi
     * Harukanaru Augusta 3 - Masters New
     * Hayashi Kaihou Kudan no Igo Taidou
     * Itoi Shigesato no Bass Tsuri No.1
     * J. League '96 Dream Stadium
     * Jikkyou Oshaberi Parodius
     * Jumpin' Derby
     * Kakinoki Shougi
     * Kirby Super Star (USA) / Hoshi no Kirby - Super Deluxe (Japan)
           / Kirby's Fun Pak (Europe)
     * Kirby's Dream Land 3 (USA) / Hoshi no Kirby 3 (Japan)
     * Marvelous
     * Mini Yonku Shining Scorpion - Let's & Go!!
     * Pebble Beach no Hatou New - Tournament Edition
     * PGA European Tour
     * PGA Tour 96
     * Power Rangers Zeo - Battle Racers
     * Saikousoku Shikou Shougi Mahjong
     * SD F-1 Grand Prix
     * SD Gundam G-NEXT cartridge ROM (G-NEXT.SFC)
     * Shin Shougi Club
     * Shougi no Hanamichi
     * Shougi Saikyou
     * Shougi Saikyou II
     * Super Bomberman - Panic Bomber W
     * Super Mario RPG
     * Super Robot Wars Gaiden
     * Super Shougi 3 - Kitaihei
     * Taikyoku Igo - Idaten
     * Takemiya Masaki Kudan no Igo Daishou

 - - - -
  S-DD1
 - - - -
     * Star Ocean
     * Street Fighter Alpha 2 (USA/Europe) / Street Fighter Zero 2 (Japan)

 - - - - - -
  Seta DSP
 - - - - - -
  Seta's DSP has 2 major firmwares.

     + Seta 10 / ST010 (supported)
         * F1 ROC II (USA) / Exhaust Heat II (Japan)
     + Seta 11 / ST011 (partially supported)
         * Hayazashi Nidan Morita Shougi

 - - - - - -
  Seta RISC
 - - - - - -
  The Seta RISC chip is not emulated.

     + Seta 18 / ST018
         * Hayazashi Nidan Morita Shougi 2

 - - - - -
  SPC7110
 - - - - -
     * Far East of Eden Zero
     * Far East of Eden Zero - Shounen Jump no Shou
     * Momotarou Dentetsu Happy
     * Super Power League 4

  ZSNES does not fully support the SPC7110 chip yet. However, you may use some
  third party graphics decompression packs to get the four above games to work.

  The SPC7110 graphic packs are mirrored on a number of sites on the Internet.
  Here are a few:

     * ipher's WIP Pages [http://other.ipherswipsite.com/gpacks/]
     * NSRT Official Site [http://nsrt.edgeemu.com]
     * Caitsith2's Personal Web Page [http://www.caitsith2.com]

  After you have downloaded all of the parts, extract them all into a new
  directory on your disk. Then go to the Config-->Paths menu in the GUI
  and enter in the location of the folder in the appropriate field.

 - - - -
  S-RTC
 - - - -
     * Daikaijuu Monogatari II

 - - - - -
  SuperFX
 - - - - -
     * Dirt Racer
     * Dirt Trax FX
     * Doom
     * Star Fox (USA / Japan) / Starwing (Europe)
     * Stunt Race FX (USA / Europe) / Wild Trax (Japan)
     * Super Mario World 2: Yoshi's Island
     * Vortex
     * Winter Gold

  ** ZSNES does not support interleaved SuperFX ROMs! **
  An interleaved ROM is one in which the data is arranged differently than in
  the original, real SNES cartridge. While ZSNES has the ability to read the
  most common types of interleaved ROMs, it cannot read interleaved SuperFX
  ROMs, or even determine that they are interleaved.

  You can use NSRT [http://nsrt.edgeemu.com] to deinterleave your SuperFX ROMs,
  or if you prefer, all your ROMs. Consequently, the creator of NSRT (Nach) has
  also written a document about the technical details of interleaved SNES ROMs,
  if you are interested.
    "The Grand Document on the many SNES Interleave Algorithms":
    [http://nsrt.edgeemu.com/forum/kb.php?mode=article&k=2]


............................................................
  4.                 Special Cartridges
............................................................

 - - - - - - - - - - - - - - -
  Same Game; SD Gundam G-Next
 - - - - - - - - - - - - - - -

  These were special games released only in Japan. They could be played by
  themselves, standing alone, but they could also be played with special
  additional cartridges, which plugged into the top of the main cartridge.
  These extra cartridges used the same form-factor as the BS-X memory
  cartridges, and they would improve or change the main game in some small way
  (similar to the Sonic and Knuckles cartridge for Sega Genesis).

  You can play the original cartridges by themselves by loading them like any
  normal ROM. In order to play these games as if they had an expansion cartridge
  plugged in, you must first configure the paths to the base cartridge ROMs
  under Config -> Paths. After defining the path to the base ROMs, you can now
  load the expansion ROM like any normal ROM. ZSNES will virtually "plug in" the
  expansion ROM to the base ROM, and load both of them at the same time.

  The NSRT file names for these ROMs are "SAMEGAME.SFC" and "G-NEXT.SFC",
  respectively.

 - - - - - - - -
  Sufami Turbo
 - - - - - - - -

  Gamers Graveyard has some pictures and information on the Sufami Turbo.
  [http://www.gamersgraveyard.com/repository/snes/peripherals/sufamiturbo.html]

  The Sufami Turbo is a special add-on, manufactured by Bandai, and released
  only in Japan. The games were sold on small, GameBoy-sized mini-cartridges,
  two of which could simultaneously be plugged into the Sufami Turbo main
  cartridge. Certain combinations of games could interact with each other.

  To emulate the Sufami Turbo, you will first need the Sufami Turbo BIOS.
  You must configure the path to this BIOS under Config-->Paths.

  The NSRT file name for the Sufami Turbo BIOS is "STBIOS.BIN".

  If you use NSRT, your Sufami Turbo ROMs will have .st extensions. In order to
  load two ROMs at once (to emulate two simultaneously loaded cartridges), you
  must use the command line. As an example, you would type in:
      zsnesw.exe "C:\Path\To\ROMs\sufami turbo rom 1.st"
        "C:\Path\To\ROMs\sufami turbo rom 2.st"
  Note that you must type the FULL path to both ROM images. The example is
  specific to the Windows command line and ZSNES port, but you get the idea.

  You may occasionally come across a Sufami Turbo ROM that is hacked to include
  the BIOS with it. Use NSRT with the -split command to separate the BIOS from
  the ROM. This will give you at least two separate files: one will be the game,
  and the other will be the BIOS. You may even get 3 files: Two games and one
  BIOS. After you have separated the BIOS and the game(s), simply follow the
  directions stated above.

 - - - - - - - - - - - - - - - -
  Broadcast Satellaview (BS-X)
 - - - - - - - - - - - - - - - -

  Please read the Satellaview article on Wikipedia for additional information.
  [http://en.wikipedia.org/wiki/Satellaview]

  This add-on was released only in Japan. It allowed gamers to connect to a
  satellite feed at certain times of the day, which would transmit games to the
  Super Famicom. Downloaded games were optionally stored on a small,
  eight-megabit mini-cartridge, which plugged into the top of the BS-X main
  cartridge (which in turn plugged directly into the Super Famicom). Many games,
  some of which had time limits, were made exclusively for the BS Satellaview.

  Currently, ZSNES can partially emulate the BS-X; some games will have graphics
  glitches, some games can be coaxed into running by changing certain settings,
  but some games won't run at all.

  Also note that there is a BIOS for the BS-X. You may configure the path to the
  BS-X BIOS under Config -> Paths; however, it's not currently required to run
  BS games. It may be required in the future.

  The NSRT file name for the BS-X BIOS is "BS Satellaview BS-X (BIOS) (J).sfc".

 - - - - - - - -
  Super GameBoy
 - - - - - - - -

  ** The Super GameBoy is not emulated. There are currently no plans to support
  it. ** This is because the Super GameBoy cartridge contains a complete set of
  GameBoy hardware (without screen and speakers, of course). Thus, to fully
  support the Super GameBoy, ZSNES would have to emulate both the SNES and a
  GameBoy. In addition, there are some very complex interactions between the
  Super GameBoy and SNES hardware that are not yet fully understood.

  "But wait," you say, "I have a Super GameBoy BIOS! Won't this allow ZSNES to
  emulate a Super GameBoy?"

  The answer is "no." The BIOS you have is only the software for the Super
  GameBoy, not the hardware, and thus is no help in emulating the Super GameBoy
  hardware. In the meantime, there are some GameBoy emulators, such as KiGB
  [http://kigb.emuunlim.com], BGB [http://bgb.bircd.org], and VisualBoyAdvance
  [http://vba.ngemu.com], that faithfully support some of the more useful
  features of the Super GameBoy.


............................................................
  5.               Individual Game Issues
............................................................

 - - - - - - - - - - - - - - - -
         Chrono Trigger
 - - - - - - - - - - - - - - - -

  How do you get past the part in Chrono Trigger where you have to press the
  L, R, and A buttons?

  Assign two or all three of these SNES controller buttons to the same keyboard
  key. You can do this under Config Menu -> Input. Please read the note about
  keyboard limitations in the Input section [GUI.txt].

 - - - - - - - - - - - - - - - -
           Star Ocean
 - - - - - - - - - - - - - - - -

  This game is difficult to emulate correctly, and there are also bugs within
  the game itself. The battles in the game are emulated at an incorrect speed,
  and the game will often freeze or crash randomly. You may encounter more
  issues. You can find detailed information about the bugs in this game at
  RPGClassics [http://www.rpgclassics.com/shrines/snes/so1/bugs.shtml].

  For best results, we recommend that you use an emulator that runs the game
  more accurately, such as Snes9x [http://www.snes9x.com].


............................................................
  6.            Games Supported by ManyMouse
............................................................

  ZSNES supports Ryan C. Gordon's ManyMouse library, which allows you to take
  advantage of games that support usage of two SNES add-on devices at once.
  [http://icculus.org/manymouse/]
  You will need two mice plugged into your computer.

  Here is a list of known games that support two SNES add-on devices
  simultaneously:

      - Arkanoid - Doh It Again
      - Bishoujo Senshi Sailor Moon S - Kondo ha Puzzle de Oshiokiyo!
      - Fun 'N Games
      - Koutetsu no Kishi (and its two sequels)
      - Lamborghini - American Challenge
      - Lord Monarch
      - Motoko-chan no Wonder Kitchen
      - Operation Thunderbolt
      - Revolution X
      - Shien's Revenge
      - Super Castles
      - T2 - The Arcade Game
      - Tin Star
      - Tokimeki Memorial

  Linux users should remember to type
      chmod a+r /dev/input/*
  at the shell after both mice are plugged in.

  This feature is not implemented in the DOS port.

  ManyMouse currently does not support BSD either, so Windows, Linux, or
  Mac OS X is required.


............................................................
  7.             List of Multiplayer Games
............................................................

Please note that this list does not include any sports games (since they are
easy to recognize and most of them are multiplayer). It also does not include
games with only 2-player alternating modes nor games that require the SNES
Mouse/Super Scope. Also, this list does not generally have sequels or other
derivatives listed; if the original is listed here, it's likely its sequels
and derivatives support multiplayer, too.


This list is not necessarily complete.

   * Aero Fighters
   * Art of Fighting
   * Battletoads in Battlemaniacs
   * Battletoads vs DoubleDragon
   * Brawl Brothers
   * Brutal: Paws of Fury
   * Captain Commando
   * Clay Fighter
   * Contra 3
   * Darius Twin
   * Double Dragon 5
   * Dragonball Z Super Butoden
   * Dragonball Z Hyper Dimension
   * Faceball
   * Fatal Fury
   * Fighter's History
   * Final Fight 2 & 3
   * Ghoul Patrol
   * Goemon
   * Goof Troop
   * Gundam Wing: Endless Duel
   * Joe & Mac
   * Jurassic Park 2 - The Chaos Continues
   * Killer Instinct
   * King of Dragons
   * King of the Monsters
   * Kirby's Avalanche
   * Kirby's Dreamland 3
   * Kirby Super Star
   * Legend of the Mystical Ninja
   * Lemmings
   * Megaman 7 (Secret Code - password 1415/5585/7823/6251 and press L+R+Start)
   * Metal Warriors
   * Mortal Kombat
   * Ms. Pac-Man
   * NP Mario Picross Series
   * Peace Keapers
   * Pirates of the Dark Water
   * Pocky & Rocky
   * Pop'n Twinbee
   * Power Instinct
   * Primal Rage
   * Puzzle Bobble
   * Raiden
   * Rampart
   * Ranma 1/2
   * Rise of the Robots
   * Rival Turf
   * Rock N' Roll Racing
   * Run Saber
   * Sailor Moon
   * Samurai Shodown
   * Secret of Mana
   * Seiken Densetsu 3
   * Shaq Fu
   * Star Fox 2
   * Star Trek Starfleet Academy
   * Street Fighter 2
   * Street Fighter 2 Turbo
   * Street Fighter Alpha 2
   * Street Racer
   * Stunt Race FX
   * Sunset Riders
   * Super Bomberman
   * Super Mario All-Stars (SMB3 minigame)
   * Super Mario Kart
   * Super Mario World 2: Yoshi's Island (At map, press X,X,Y,B,A)
   * Super Offroad
   * Super Smash TV
   * Super Street Fighter 2
   * Suzuka 8 Hours
   * Teenage Mutant Ninja Turtles 4 - Turtles in Time
   * Teenage Mutant Ninja Turtles 5 - Tournament Fighters
   * Tetris
   * The Great Circus Mystery
   * Top Gear 2
   * Top Gear 3000
   * Tuff E Nuff
   * Ultimate Mortal Kombat 3
   * Uniracers
   * Wild Guns
   * World Heroes
   * Wrecking Crew '98
   * Zombies Ate My Neighbors


. . . . . . . . . . . . . . . .

    - ZSNES Team & ZSNES Documentation Team
    - Ported by: "https://thegamesss.github.io/"
