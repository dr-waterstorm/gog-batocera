# DOSBox Staging

Set as the default for "DOS" games.

This can be done by selecting the "DOS" category in Batocera, pressing the `Backspace` key and setting DOSBox Staging as the default emulator.

Note: This may break games that worked with the standard DOSBox or DOSBoxX.

## General Sound Setup

### FluidSynth

Download the preferred SoundFont as recommended in the official [DOSBox Staging MIDI fluidsynth docs](https://github.com/dosbox-staging/dosbox-staging/wiki/MIDI#fluidsynth), copy it to `/userdata/system/configs/dosbox/soundfonts` and adjust `dosbox-staging.conf` in `/userdata/system/configs/dosbox/` to match the selected/downloaded file.

Recommended SoundFonts by DOSBox Staging can be found [here](https://github.com/dosbox-staging/dosbox-staging/wiki/MIDI#soundfonts).

For example:

```
[midi]
mididevice = fluidsynth

[fluidsynth]
soundfont = GeneralUser-GS.sf2
```

### Roland MT32

To get even better sound in some games, you can use a real Roland MT-32 MIDI device, and/or follow the [DOSBox Staging MIDI docs](https://github.com/dosbox-staging/dosbox-staging/wiki/MIDI) to set up MT-32 emulation. Note that the MT-32 ROM files required for emulation are copyrighted by Roland Corporation.

## General Game Setup

### Copy Game Data
This section describes how to extract the game files and move them to Batocera.

This can be done in various ways, for example:
- Download the game from GOG.com
  - Install the game
  - Extract the installer
- Use GOG Galaxy to install the game
- Install the game vie Heroic Games Launcher

In my case, I downloaded and installed the game on a Bazzite machine using Heroic Games Launcher.
However, this is just an optional "helper".

After extracting or installing the game copy the game folder to the Batocera machine under `/userdata/roms/dos/{GAME_NAME}.{ENDING}`.
More details to the specific rom folders in the individual readme files.

This can either be done using the CIFS share over network or using a USB Stick.

Usually some unneeded files can be removed after copying the game files.
This is also described in more detail in the individual readme files.

### Starting the Game

Batocera uses a file called `dosbox.bat` in the root of the game folder to launch the game with DOSBox Staging.

### Config Override

You can also add an additional `dosbox.conf` in the root of the game folder to override the default configuration.

## Starting DOSBox Staging manually

This can be done by pressing `F1` in the Batocera main menu (this does not work inside the game
selection of a rom type, such as MSDOS). 

1. Go to applications and start the `xterm`
2. Navigate to the folder of the game, using `cd /userdata/roms/dos/{GAME}.{TYPE}`
3. Start DOSBox Staging with `dosbox-staging`
