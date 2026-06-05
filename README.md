# Final Fantasy V PSX Script Research

This repository documents the text encoding used by the PlayStation release of Final Fantasy V.

The primary discovery is that the file:

```
NAR/FF5_MESS.BIN
```

contains the game's script in a format that closely corresponds to the RPGe SNES translation. After decoding, most dialogue lines can be aligned directly with the RPGe script, aside from two large blocks of padding data.

This repository contains:

* Documentation of the text format
* A partially documented character table
* Notes on control codes
* Example extraction tools
* An IPS patch used during research

No game files are distributed.

Users must extract FF5_MESS.BIN from their own legally obtained copy of Final Fantasy V.


# What is currently unknown

where the rest of the text in-game is located.
There's stuff pertaining to character names and jobs in DEO.BIN and monsters might be in BTL\FF5_BTL2.BIN 
I don't know where item names or monster names are located. 

* The IPS patch includes the current work at backporting the "interesting" translation of everything else from the game as well

Currently it includes:
* The script ripped from the Playstation
* Monster, Character, Location and Job Names manually added from online sources (finalfantasy.fandom.com)