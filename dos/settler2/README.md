# The Settlers 2 GOLD / Die Siedler 2 GOLD

I'm using the [GOG version](https://www.gog.com/de/game/the_settlers_2_gold_edition)

## General Setup

I downloaded and installed the game on a Bazzite machine using Heroic Games Launcher.
This is just an optional "helper" and you can also simply install directly from GOG, use GOG Galaxy or extract the installer directly.

After installing the game I remove the `DOSBOX` folder, as it is not needed in batocera.
In addition we could clean up even more files but it's not needed to run the game and they only take up a few megabytes of disk space.

I copied all the remaining files the installation folder to the Batocera machine under `/userdata/roms/dos/siedler-2-gold.pc`.
This can either be done using the CIFS share over network or using an USB Stick.

## DOSBox Staging setup

To make this work in DOSBox staging there are several steps:

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
