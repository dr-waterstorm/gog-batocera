# GOG to Batocera

## General Goal
This repo documents the progress of importing my GOG games into batocera. The primary focus is to get my GOG games working on my batocera stating using dosbox-staging, scummvm and wine / proton.

## My Setup
I use the following hardware:

- Slimboook One from 2025 - [Link](https://slimbook.com/en/one)
- Checkmate 19" IPS Retro Monitor - [Link](https://checkmate1500plus.com/IntroductionDisplays.aspx)
- Drop tenkeyless Lord of the Rings Keyboard
- Razer Viper V3 HyperSpeed
- 2x Xbox One Controller (via USB)

## Batocera

Currentyl I'm running Batocera 

In the following I describe a few important settings that I changed

### Video

To fit to the `5:4` `1240x1024` resolution of the monitor I've adjuste the configs and settings to this:

In `batocera.conf` in `/userdata/system/`

```
global.videooutput=HDMI-1
global.ratio=5/4
```

### Audio

#### Fluidsynth

Install sound font

Then adjust `dosbox-staging.conf` in `/userdata/system/configs/dosbox/`

```
[midi]
mididevice = fluidsynth

[fluidsynth]
soundfont = GeneralUser-GS.sf2
```

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
