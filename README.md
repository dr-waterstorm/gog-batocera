# GOG to Batocera

## General Goal
This repo documents the progress of importing my GOG games into batocera.
The primary focus is to get my GOG games working on my Batocera using DOSBox Staging, ScummVM and Wine / Proton with the out of the box tools of Batocera.

## My Setup
I use the following hardware:

- Slimboook One from 2025 - [Link](https://slimbook.com/en/one)
- Checkmate 19" IPS Retro Monitor - [Link](https://checkmate1500plus.com/IntroductionDisplays.aspx)
- Drop tenkeyless Lord of the Rings Keyboard
- Razer Viper V3 HyperSpeed
- 2x Xbox One Controller (via USB)

## Batocera

Currently, I'm running the following setup:

- Batocera 42 installed to the internal SSD (can be done using a live stick and installing via the system settings)
- DOSBox Staging set as default (instead of DOSBox, as it brings many improvements over the standard DOSBox and I do like the out-of-the-box scaling and shaders)
- Stamdalone ScummVM set as default (instead of Libretro: ScummVM, as it usually brings a newer version and therefore improvements over the Libretro version)

In the following sections I describe a few important settings that I changed.

### Video

To fit to the `5:4` `1280x1024` resolution of the monitor I've adjuste the configs and settings to this:

System settings:
Videomode: 1280x1024 75.02 HZ

In `batocera.conf` in `/userdata/system/`

```
global.ratio=5/4
```

### Different keyboard layout than OS language
I'm using German as the primary language of Batocera, but I have a US ANSI keyboard layout. This can be configured via the `batocera.conf` in `/userdata/system/`

```
system.language=de_DE
system.kblayout=us
```

In addition to also apply this to DOSBox Staging adjust `dosbox-staging.conf` in `/userdata/system/configs/dosbox/`

```
[dos]
keyboardlayout = us
```

### DOSBox Staging

See [here](./dos/README.md) for more information about the setup of DOSBox Staging.

### ScummVM

See [here](./scummvm/README.md) for more information about the setup of ScummVM.

## Games

All referenced games were either bought on [GOG](https://www.gog.com/) or I have the original physical copy in my collection.

The documentation for each game and the steps necessary to make them work are documented in separate folders in this GIT repository. I may or may not later on add scripts to the repos to automate the installation.

### List of Games

This is a list of all the games I've imported so far.

#### DOS

##### Done
| Game                                                  | Languages | Developer | Source                                                           |
|-------------------------------------------------------|-----------|-----------|------------------------------------------------------------------|
| [Albion](./dos/albion/README.md)                      | `en`/`de` | Blue Byte | [GOG](https://www.gog.com/en/game/albion)                        |
| Die Fugger II                                         | `de` | Sunflowers | [original CD](https://de.wikipedia.org/wiki/Die_Fugger_II)       |
| [Sensible World of Soccer '96/'97](./dos/swos/README.md)       | `en`/`de`/`fr`/`it` | Renegade | [GOG](https://www.gog.com/en/game/sensible_world_of_soccer_9697) |
| [The Settlers 2 Gold](./dos/the_settlers_2/README.md) | `en`/`de` | Blue Byte | [GOG](https://www.gog.com/en/game/the_settlers_2_gold_edition)   |

##### In progress
| Game                                                  | Languages | Developer | Source                                                           |
|-------------------------------------------------------|-----------|-----------|------------------------------------------------------------------|
| Pirates Gold                                          | `en`/`de` | MicroProse | [GOG](https://www.gog.com/en/game/pirates_gold_plus)             |


#### ScummVM
| Game                   | Languages | Developer | Source                                                |
|------------------------|-----------|-----------|-------------------------------------------------------|
| The Legend of Kyrandia | `en`/`de` | Westwood Studios | [GOG](https://www.gog.com/en/game/legend_of_kyrandia) |

#### Windows
| Game | Languages | Developer | Source |
|------|-----------|-----------|--------|
| Mashed | `en`      | Supersonic Software | [GOG](https://www.gog.com/en/game/mashed) |
| Robin Hood: The Legend of Sherwood | `de`/`en` | Spellbound Entertainment | [GOG](https://www.gog.com/en/game/robin_hood) |
| Die Gilde Gold | `de`/`en`  | 4HEAD Studios | [GOG](https://www.gog.com/en/game/the_guild_gold_edition) |
| Might and Magic VI | `de`/`en` | New World Computing | [GOG](https://www.gog.com/en/game/might_and_magic_6_limited_edition) |

### Scraping Games

You can use the integrated [Batocera Scraper](https://wiki.batocera.org/scrape_from) to scrape metadata for the games from various sources.