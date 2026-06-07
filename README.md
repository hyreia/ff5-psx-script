# Final Fantasy V PSX Script

This repository documents finding the text inside the PlayStation release of Final Fantasy V.
As proof of concept, I've created a patch for the SNES version of the game that includes the Playstation script.
Now you can experience the game as an approximation of what it would have been like if it came out in America: 
...interestingly translated!

The primary discovery is that the file:
```
NAR/FF5_MESS.BIN
```
contains the game's script in a format that closely corresponds to the RPGe SNES translation. After decoding, most dialogue lines can be aligned directly with the RPGe script, aside from two large blocks of padding data.

```
BTL/FF5_BTL.BIN
```
Contains all text that appears in battle as well as monster data (stat blocks and probably formations too.)

This repository contains:

* Documentation of the text format
* A partially documented character table
* Notes on control codes
* Example extraction tools
* An IPS patch used during research

No game files are distributed.

# Currently the patch includes:
* The dialogue ripped from the Playstation
* The monsters, abilities, spells... pretty much all text that appears in battle taken directly from the PS1 disc (very minor changes were made to fit a few in)
* Character names changed to match the PS1 Script

# What is currently unknown
* Where the job ability descriptions and item descriptions are. They're around here somewhere. Maybe DEO.BIN? It might be a mercy to leave them as-is so that you can recognize them.
* Monster formations, I guess?
* Where a lot of non-script stuff is stored, that's not part of this exercise or mod.

## How to Use the Patch:
* Get a patching program such as Lunar IPS
* Download the patch (Final Fantasy V Anthology Script.ips)
* Legally acquire Final Fantasy V (J) [T+Eng1.1_RPGe].smc (It might work with others, but it expects the expanded RPGe ROM)
* Apply patch with Lunar IPS 

### The unofficial RPGe script compared to the official Playstation Anthology script:
https://docs.google.com/spreadsheets/d/10kWyhaSkz3ZOLB6XqFbLZChQoSeLQq03tq150Xaf7I4/edit?usp=sharing

### I am not responsible for any breaking or damage you do with this.
That said, this is purely a text hack so if your game crashes you can try moving your save file to a clean RPGe translation. It should work fine. 