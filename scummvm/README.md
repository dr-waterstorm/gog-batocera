# ScummVM

As mentioned I set the default to standalone `ScummVM`

This can be done by selecting the "ScummVM" category in Batocera, pressing the `Backspace` key and setting ScummVM as the default emulator.

## General Video / Shader Setup

I'm using a CRT shader as I played most of the games on an old CRT monitor back in the day and I do like the effect.

To set this up press `F1` in the main menu, go to applications and start `scummvm-config`. In general options I selected:

- Graphics mode: `OpenGL`
- Scaling: `Normal - 1x`
- Shader: `crt/crt-easymode.glslp`

## General Audio Setup

### Roland MT32

Similar to [DOSBox Staging](../dos/README.md#roland-mt32), you can set up a real Roland MT-32 MIDI device or use emulation in ScummVM. This can be set in the `MIDI` / `MT32` options.

## General Game Setup

This section describes how to extract the game files and move them to Batocera.

This can be done in various ways, for example:
- Download the game from GOG.com
    - Install the game
    - Extract the installer
- Use GOG Galaxy to install the game
- Install the game vie Heroic Games Launcher

In my case, I downloaded and installed the game on a Bazzite machine using Heroic Games Launcher.
However, this is just an optional "helper".

After extracting or installing the game copy the game folder to the Batocera machine under `/userdata/roms/scummvm/{GAME_NAME}.{ENDING}/`.
More details to the specific rom folders in the individual readme files.

This can either be done using the CIFS share over network or using a USB Stick.

Usually, only the actual game / data files are needed.
This is also described in more detail in the individual readme files.
