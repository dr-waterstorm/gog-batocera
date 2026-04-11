# Sensible World of Soccer '96/'97 (SWOS)

This guide uses the [GOG version](https://www.gog.com/en/game/sensible_world_of_soccer_9697)

![](https://img.shields.io/badge/complexity-medium-orange)

## Game Setup

### General
Follow the general game setup instructions [here](../README.md#general-game-setup).

> [!NOTE]
> I downloaded the Linux version, which has a different folder structure. The Windows version certainly works as well, but needs a few adjustments to work.

### Specific
Copy the game files to:
```
/userdata/roms/dos/sensible-world-of-soccer-96-97.pc
```

### Cleanup
I removed the `DOSBOX` folder, as it is unnecessary in batocera.
In addition, we could clean up even more files, but it's unnecessary to run the game,
and they only take up a few megabytes of disk space.

## DOSBox Staging setup

To make this work in DOSBox Staging, there are several steps. 
Some of the changes I made are purely cosmetic and may not be needed.

### Rename and move the CD image

1. Create a new folder for the CD image called `cd` via the file manager (F1 in the Batocera main menu) or via the CLI using `mkdir /userdata/roms/dos/sensible-world-of-soccer-96-97.pc/cd`
2. Move `data/SWOS97.DAT` to `cd/SWOS97.iso`


### Create the config files

#### dosbox.bat
Create a `dosbox.bat` in `/userdata/roms/dos/sensible-world-of-soccer-96-97.pc/` that Batocera will automatically launch and put the following content inside or use the `dosbox.bat` provided [here](./dosbox.bat).

```
imgmount d "cd/SWOS97.iso" -t iso -fs iso
cd data
german.exe
```

> [!NOTE]
> Replace `german.exe` with `english.exe`, `italian.exe` or `french.exe` for the specific language support.

#### dosbox.conf

For this game we'll create a `dosbox.conf` in `/userdata/roms/dos/sensible-world-of-soccer-96-97.pc/` that will override the Batocera DOSBox Staging default config.

This is needed to make the controller(s) work correctly and in case of my monitor to improve on the display / scaling of the video.

Put the following content inside or use the `dosbox.conf` provided [here](./dosbox.conf).

```
[render]
integer_scaling = off

[joystick]
joysticktype = 2axis
timed = false
```

> [!NOTE]
> If you do not have a monitor with a special resolution like I do you can remove the `[render]` part of the config.

### Audio and joystick setup

#### 2 Player Setup

For 2 player setup it's very important to note that there is a bug in this version of SWOS, that prevents the usage of both controllers out of the box. If you select "2 joysticks" in the setup the game will crash once you move both analog sticks at the same time.

Therefore the workaround here is to use `keyboard + joystick` in the setup and either play with keyboard and controller or map the keyboard input to a second controller. I'll describe how to do this in the following.

#### Audio

Select a appropriate audio device for your setup. For my setup I've chosen:

```
MIDI Music: General MIDI (Roland MPU-401 interface or 100% compatible)
Digital Effects: Creative Labs Sound Blaster 16 or AWE32
```

#### Setup & Calibration

In order to setup and calibrate the joystick, you have to run the `INSTALL.EXE` via `dosbox-staging`.

1. Follow the instructions on how to start DOSBox Staging manually [here](../README.md#starting-dosbox-staging-manually)
2. Mount the `C` drive using `mount c .`
3. Navigate to the game directory with `c:`
4. Mount the CD using `imgmount d cd/SWOS97.iso -t iso -fs iso`
5. Go to the data folder `cd data`
6. Start the setup with `INSTALL.EXE`
7. Select your desired language
8. Go to Settings
9. Setup the sound as described [above](#audio)
10. Setup the input as described [above](#2-player-setup)
11. Save the settings and exit

#### [Optional] Map the keyboard to a controller

If you want to play with 2 controllers instead of keyboard + controller you can do so by selecting the game in Batocera, opening the game options (long press on ENTER) and selecting `Create padtokey-profile`.

This will allow you to map the keyboard that you have just set-up in the `install.exe` to the second controller. Make sure you do not use the same controller as in the setup above.

## Update Game List and Metadata

Update the game list in the settings (space in the main menu) for the game to show up.

For images and metadata use the [Batocera scraper](../../README.md#scraping-games).

My `gamelist.xml` entry for this game looks like this:

```xml

```