# Albion

This guide uses the [GOG version](https://www.gog.com/de/game/albion)

![](https://img.shields.io/badge/complexity-easy-brightgreen)

## Game Setup

### General
Follow the general game setup instructions [here](../README.md#general-game-setup).

### Specific
Copy the game files to:
```
/userdata/roms/dos/albion.pc
```

### Cleanup
I removed the `DOSBOX` folder, as it is unnecessary in batocera.
In addition, we could clean up even more files, but it's unnecessary to run the game,
and they only take up a few megabytes of disk space.

## DOSBox Staging setup

To make this work in DOSBox Staging, there are several steps:

### Create the config file

Create a `dosbox.bat` that Batocera will automatically launch and put the following content inside or
use the `dosbox.bat` provided [here](./dosbox.bat).

```
imgmount d game.ins -t cdrom
albion.exe
```

This will mount the CD and start the game.

## Game Setup

The game usually runs fine with the defaults, but if you want, you can start the provided setup to tweak the settings:

1. Follow the instructions on how to start DOSBox Staging manually [here](../README.md#starting-dosbox-staging-manually)
2. Mount the `C` drive using `mount c .`
3. Navigate to the game directory with `c:`
4. Mount the CD using `mount d game.ins -t cdrom`
5. Start the setup with `SETUP.EXE`

## Update Game List and Metadata

Update the game list in the settings (space in the main menu) for the game to show up.

For images and metadata use the [Batocera scraper](../../README.md#scraping-games).

My `gamelist.xml` entry for this game looks like this:

```xml
	<game id="155726">
		<path>./albion.pc</path>
		<name>Albion</name>
		<desc>Wir schreiben das Jahr 2227. Die mächtige DDT Corporation hat ein Fabrikschiff namens Toronto ausgesandt, um Mineralien und Ressourcen von Albion zu ernten, einer neu entdeckten Welt, die angeblich lebensfeindlich, aber reich an Ressourcen ist. Der Raumpilot Tom Driscoll soll auf dem Planeten atmosphärische Messungen vornehmen, stürzt aber nach einem scheinbar zufälligen Systemausfall seines Shuttles ab. Nachdem er sich von dem Unfall erholt hat, muss er schockiert feststellen, dass Albion in Wirklichkeit eine reiche, von Leben erfüllte Welt ist, die von verschiedenen Rassen mit ihren einzigartigen Kulturen bewohnt wird. Es ist nun seine Aufgabe, die seltsame neue Welt zu erkunden, ihren Bewohnern zu helfen und schließlich den Weg zurück nach Toronto zu finden..</desc>
		<image>./images/albion-image.png</image>
		<marquee>./images/albion-marquee.png</marquee>
		<thumbnail>./images/albion-thumb.png</thumbnail>
		<fanart>./images/albion-fanart.jpg</fanart>
		<rating>0.8</rating>
		<releasedate>19951231T000000</releasedate>
		<developer>Blue Byte</developer>
		<publisher>Blue Byte</publisher>
		<genre>Rollenspiele</genre>
		<players>1</players>
		<lang>de,en</lang>
	</game>
```
