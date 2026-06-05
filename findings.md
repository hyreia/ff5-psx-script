# Findings

## Final Fantasy V PlayStation Script Research

This repository contains notes and tools related to extracting and decoding the English script from the PlayStation release of Final Fantasy V.

## Script Location

The complete English script is stored in:

```
NAR/FF5_MESS.BIN
```

inside the PlayStation disc image.

The file can be viewed by mounting the game image and opening it as a data disc.

## Relationship to the RPGe Translation

The text in `FF5_MESS.BIN` appears to correspond directly to the classic RPGe translation script. 
RPGe likely kept the script in order, no reason not to!


Observations:

* Script lines generally match the RPGe script line-for-line.
* Two large blocks of zero bytes appear in the PlayStation file.
* Aside from these gaps, the text order closely follows the RPGe release.

## Character Encoding

The game uses a custom single-byte encoding.

### Basic Character Set

* `02-1B` = uppercase letters A-Z
* `1C-35` = lowercase letters a-z
* `36-3F` = digits 0-9
* `63` = normal space

### Common Punctuation

| Hex | Character |
| --- | --------- |
| 40  | !         |
| 41  | ?         |
| 42  | /         |
| 43  | :         |
| 44  | "         |
| 45  | '         |
| 46  | -         |
| 47  | .         |
| 48  | ,         |
| 49  | …         |
| 50  | ;         |
| 51  | #         |
| 52  | +         |
| 53  | (         |
| 54  | )         |
| 55  | %         |
| 56  | ~         |
| 57  | $         |

### Controller Symbols

| Hex | Symbol |
| --- | ------ |
| 58  | ●      |
| 59  | ✖      |
| 60  | ■      |
| 61  | ▲      |

## Dictionary Compression

The encoding uses common words and syllables as single-byte tokens.

Examples:

| Hex | Expansion |
| --- | --------- |
| 80  | and       |
| 81  | about     |
| 82  | be        |
| 83  | crystal   |
| 86  | Dragon    |
| 87  | Faris     |
| 89  | Galuf     |
| 8F  | Krile     |
| 93  | Reina     |
| 96  | the       |
| 97  | this      |
| 98  | that      |
| 9C  | you       |
| A4  | ing       |
| A6  | to        |
| A7  | th        |

This significantly reduces script size.

## Control Codes

Known control codes:

| Hex | Meaning                                        |
| --- | ---------------------------------------------- |
| 00  | End of line / terminator                       |
| 01  | EOL marker                                     |
| F0  | Wait                                           |
| F1  | Bartz name token                               |
| F2  | Delay                                          |
| F4  | Unknown control code                           |
| F5  | Unknown control code, possibly textbox control |

Additional control sequences remain undocumented.

## Existing Tools

The repository includes:

* Character table (JSON format)
* Simple Python decoder
* IPS patch
* Documentation of the PlayStation text format

## ROM Editor Compatibility

The script was imported into the SNES ROM with:

```
FF5e_Text_Editor v1.07.exe
```

with the ROM file:

```
Final Fantasy V (J) [T+Eng1.1_RPGe].smc
```

Other ROM revisions may not be compatible.