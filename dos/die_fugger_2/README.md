# Die Fugger II

This guide uses the original CD (bought from ebay).

![](https://img.shields.io/badge/complexity-medium-orange)

## Game Setup

### Rip the CD

In order to use the CD in DOSBox Staging we need to rip it to a common format that DOSBox can read. For this I used the standard `bin` and `cue` formats.

On Linux this can be done easily using `cdrdao`.

Put the CD in the drive and use:

```
cdrdao read-cd --read-raw --datafile game.bin --device /dev/sr0 --driver generic-mmc-raw game.toc
```

This will create the basic image in `bin` format and a corresponding `toc`.

Now we need to create the `cue` file from the TOC so DOSBox knows where the music is on the CD. This can be done using:

```
toc2cue game.toc game.cue
```

Afterwards we will have a `game.bin` and a `game.cue` we can use in DOSBox Staging.


### Copy the CD image
Copy the CD files to:
```
/userdata/roms/dos/fugger2.pc
```

and rename them to `Fugger2.bin` and `Fugger2.cue`

### Start the Installation

As we do not have any game files yet, we need to use DOSBox Stating to mount the image and start the installation on the hard drive:

1. Follow the instructions on how to start DOSBox Staging manually [here](../README.md#starting-dosbox-staging-manually)
2. Mount the `C` drive using `mount c .`
3. Mount the CD using `imgmount d Fugger2.cue -t cdrom`
4. Navigate to the CD via `d:`
5. Start the setup with `INSTALL.BAT`

This will start the install wizard. The following section is in German, as I do have a German copy of the game from ebay.

### Install Wizard

Im Installations-Assistenten habe ich folgende Einstellungen für die Grund-Installation gewählt:

```
Version: 32.768 Farben Normal - 51 MB
c:\fugger2 (Standard, mit Enter bestätigen und auf Installieren klicken)
```

Soundkarten:

```
Roland LAPC-J
Automatische Erkennung -> Egal
330 hex - Irq 2
Soundkarte aktivieren
```

Nach der Einstellung der Soundkarte mit Rechts-Klick den Installations-Assistenten beenden.

Fertig, DOSBox Staging kann nun mit Alt+F4 beendet werden.

## DOSBox Staging setup

### Create the config files

#### dosbox.bat

Create a `dosbox.bat` in `/userdata/roms/dos/fugger2.pc/` that Batocera will automatically launch and put the following content inside or
use the `dosbox.bat` provided [here](./dosbox.bat).

```
imgmount d Fugger2.cue -t cdrom
c:
cd FUGGER2
FUGGER2.EXE
```

This will mount the CD, navigate to the appropriate folder and start the game.

#### dosbox.conf

For this game we'll create a `dosbox.conf` in `/userdata/roms/dos/fugger2.pc/` that will override the Batocera DOSBox Staging default config.

This is needed if you selected `Roland LAPC-J` in the sound settings as described [above](#install-wizard).

Put the following content inside or use the `dosbox.conf` provided [here](./dosbox.conf).

```
[midi]
mididevice = mt32
```

### Update Game List and Metadata

Update the game list in the settings (space in the main menu) for the game to show up.

For images and metadata use the [Batocera scraper](../../README.md#scraping-games).

My `gamelist.xml` entry for this game looks like this:

```xml

```
