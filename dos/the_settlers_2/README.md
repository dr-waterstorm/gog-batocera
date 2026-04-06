# The Settlers 2 GOLD / Die Siedler 2 GOLD

I'm using the [GOG version](https://www.gog.com/de/game/the_settlers_2_gold_edition)

## Game Setup

### General
Follow the general game setup instructions [here](../README.md#general-game-setup).

### Specific
Copy the game files to:
```
/userdata/roms/dos/settlers-2-gold.pc
```

Or for a German name: `/userdata/roms/dos/siedler-2-gold.pc`

### Cleanup
I removed the `DOSBOX` folder, as it is unnecessary in batocera.
In addition, we could clean up even more files, but it's unnecessary to run the game,
and they only take up a few megabytes of disk space.

## DOSBox Staging setup

To make this work in DOSBox Staging, there are several steps:

1. Rename `SETTLERS2.gog` to `S2.BIN` and `SETTLERS2.ins` to `S2.CUE`
2. Modify `S2.CUE` and change the first line `FILE "SETTLERS2.gog" BINARY` to `FILE "S2.BIN" BINARY` 
3. Create a `dosbox.bat` that Batocera will automatically launch and put the following content inside:
```
imgmount d S2.CUE -t cdrom
@VIDEO\SMACKPLY VIDEO\INTRO.SMK
s2.exe
```

## Update Game List and Metadata

TODO
