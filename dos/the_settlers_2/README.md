# The Settlers 2 Gold / Die Siedler 2 Gold

This guide uses the [GOG version](https://www.gog.com/de/game/the_settlers_2_gold_edition)

![](https://img.shields.io/badge/complexity-easy-brightgreen)

## Game Setup

### General
Follow the general game setup instructions [here](../README.md#general-game-setup).

### Specific
Copy the game files to:
```
/userdata/roms/dos/settlers-2-gold.pc
```

You can also choose a German name if you like: `/userdata/roms/dos/siedler-2-gold.pc`

### Cleanup
I removed the `DOSBOX` folder, as it is unnecessary in batocera.
In addition, we could clean up even more files, but it's unnecessary to run the game,
and they only take up a few megabytes of disk space.

## DOSBox Staging setup

To make this work in DOSBox Staging, there are several steps:

### Filename Mangling issue

DOSBox Staging does shorten long filenames, this is called `filename mangling`.
This caused issues for me when trying to mount the cd, as the file was not found. 

This can be easily fixed by renaming the files. While we're at it we use the standard `cue` and `bin` 
naming conventions, instead of the custom `gog` and `ins`:

1. Rename `SETTLERS2.gog` to `S2.BIN` and `SETTLERS2.ins` to `S2.CUE`
2. Modify `S2.CUE` and change the first line `FILE "SETTLERS2.gog" BINARY` to `FILE "S2.BIN" BINARY` 

### Create the config file

Create a `dosbox.bat` in `/userdata/roms/dos/settlers-2-gold.pc` that Batocera will automatically launch and put the following content inside or
use the `dosbox.bat` provided [here](./dosbox.bat).

```
imgmount d S2.CUE -t cdrom
@VIDEO\SMACKPLY VIDEO\INTRO.SMK
s2.exe
```

This will mount the CD to play music, play the intro video and start the game.

## Update Game List and Metadata

Update the game list in the settings (space in the main menu) for the game to show up.

For images and metadata use the [Batocera scraper](../../README.md#scraping-games).

My `gamelist.xml` entry for this game looks like this:

```xml
<game>
		<path>./siedler-2-gold.pc</path>
		<name>Die Siedler II: Gold Edition</name>
		<desc>The Settlers II (Gold Edition) contains:
The Settlers II: Veni, Vidi, Vici
The Settlers II Mission CD
A full world atlas
Contest entries of 130 fan-made custom maps

Veni, Vidi, Vici is the sequel of the well-known Settlers game. You start your settlement with only one main building. To build any other buildings, you first must find a source for stones and wood. So you start to build little roads where your men transport all the different goods along. There exist more than 30 different professions your men can have, and many different building types. Of course, there are other settlers in your area, too, so war is unavoidable.

The graphics are now in SVGA, and the soundtrack is available as CD-Audio or MIDI.</desc>
		<image>./images/siedler-2-gold-image.jpg</image>
		<marquee>./images/siedler-2-gold-marquee.png</marquee>
		<thumbnail>./images/siedler-2-gold-thumb.png</thumbnail>
		<fanart>./images/siedler-2-gold-fanart.jpg</fanart>
		<rating>0.85</rating>
		<releasedate>19970101T000000</releasedate>
		<developer>Blue Byte</developer>
		<publisher>Blue Byte</publisher>
		<genre>Simulation</genre>
		<players>2</players>
		<lang>de</lang>
	</game>
```