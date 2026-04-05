# GOG to Batocera

## General Goal
This repo documents the progress of importing my GOG games into batocera. The primary focus is to get my GOG games working on my batocera using DOSBox Staging, scummvm and wine / proton.

## My Setup
I use the following hardware:

- Slimboook One from 2025 - [Link](https://slimbook.com/en/one)
- Checkmate 19" IPS Retro Monitor - [Link](https://checkmate1500plus.com/IntroductionDisplays.aspx)
- Drop tenkeyless Lord of the Rings Keyboard
- Razer Viper V3 HyperSpeed
- 2x Xbox One Controller (via USB)

## Batocera

Currentyl I'm running Batocera 42 installed to the internal SSD (can be done using a live stick and installing via the system settings).

In the following sections I describe a few important settings that I changed.

### Video

To fit to the `5:4` `1280x1024` resolution of the monitor I've adjuste the configs and settings to this:

System settings:
Videomode: 1280x1024 75.02 HZ

In `batocera.conf` in `/userdata/system/`

```
global.ratio=5/4
```

### Audio

#### Fluidsynth

Download the preferred SoundFont as recommended in the official [DOSBox Staging MIDI fluidsynth docs](https://github.com/dosbox-staging/dosbox-staging/wiki/MIDI#fluidsynth), copy it to `/userdata/system/configs/dosbox/soundfonts` and adjust `dosbox-staging.conf` in `/userdata/system/configs/dosbox/` to match the selected/downloaded file.

For example:

```
[midi]
mididevice = fluidsynth

[fluidsynth]
soundfont = GeneralUser-GS.sf2
```

#### Roland MT32

To get even better sound in some games you can use a real Roland MT-32 MIDI device, and/or follow the [DOSBox Staging MIDI docs](https://github.com/dosbox-staging/dosbox-staging/wiki/MIDI) to set up MT-32 emulation. Note that the MT-32 ROM files required for emulation are copyrighted by Roland Corporation.

### Different keyboard layout than OS language
I'm using German as the primary language of Batocera, but I have a US ANSI keyboard layout. This can be configured via the `batocera.conf` in `/userdata/system/`

```
system.language=de_DE
system.kblayout=us
```

In addition to also apply this to dosbox-staging adjust `dosbox-staging.conf` in `/userdata/system/configs/dosbox/`

```
[dos]
keyboardlayout = us
```

## Games

All referenced games were either bought on [GOG](https://www.gog.com/) or I have the original physical copy in my collection.

The documentation for each game and the steps necessary to make them work are documented in separate folders in this GIT repository. I may or may not later on add scripts to the repos to automate the installation.
