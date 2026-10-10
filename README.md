These are fixes for the 9-pin version of the RetroBit controller ([Genesis](https://retro-bit.com/controllers/genesis/#console) or [Mega Drive](https://retro-bit.com/controllers/mega-drive/#console)).

All patches have been tested on real hardware (Mega Drive with a Mega EverDrive PRO).

## Fixed

| Game | What the patch fixes |
|---|---|
| Lost Vikings | The game doesn't register the C button. |
| Phantom 2040 | C (jump) and Start don't work, so you can't reach the pause menu to set punch on A. With this patch, **use MODE instead of Start**, as the RetroBit Start key is unreliable. |
| Mega-CD / Sega CD BIOS | The BIOS screen needs Start + C to get past. With this patch, **MODE works as Start**. |
| NHL '94 (Sega CD) | "Press Start" screens sometimes need Start + C. With this patch, **MODE works as Start**. Note: the patch removes support for EA's 4 Way Play (4-player) adapter. |

## Patch files

Apply the patches with any IPS patcher, e.g. [Floating IPS](https://www.romhacking.net/utilities/1040/) or [Rom Patcher JS](https://www.marcrobledo.com/RomPatcher.js/). They only work on the exact files below. Check the CRC32 of your file before patching.

| Patch | Apply to | Size | CRC32 |
|---|---|---|---|
| `Lost Vikings RetroBit C fix.ips` | Lost Vikings, The (Europe) (En,Fr,De) | 1 MB | `1F14EFC6` |
| `Phantom 2040 (4) [!] RetroBit fix.ips` | Phantom 2040 (USA) | 2 MB | `FB36E1F3` |
| `Phantom 2040 (8) RetroBit fix.ips` | Phantom 2040 (Europe) | 2 MB | `B024882E` |
| `mcd-eu BIOS RetroBit fix.ips` | Mega-CD (Europe) Model 1 BIOS v1.00 | 128 KB | `529AC15A` |
| `mcd-us BIOS RetroBit fix.ips` | Sega CD (USA) Model 1 BIOS v1.10 | 128 KB | `C6D10268` |
| `mcd-jp BIOS RetroBit fix.ips` | Mega-CD (Japan) Model 1 BIOS v1.00p | 128 KB | `9D2DA8F2` |
| `NHL '94 (USA) (Track 01) RetroBit fix.ips` | `NHL '94 (USA) (Track 01).bin` from the cue/bin set | 209,363,280 bytes | `BB13C98D` |

- **BIOS:** on the Mega EverDrive PRO, the patched files replace `mcd-eu.BIN`, `mcd-us.BIN` and `mcd-jp.BIN` in `MEGA/bios/` on the SD card. Keep a backup of the originals.
- **NHL '94:** patch only Track 01 and keep the other tracks and the `.cue` file as they are. The patch also updates the CD sector checksums (EDC/ECC) for the changed sectors.

## Tested, no issues found

* Mega Drive
  - Garfield: Caught in the Act
  - Golden Axe 2
  - The Jungle Book
  - Son of Chuck (Genesis US and Mega Drive EU)
  - Streets of Rage 3
  - Terminator 2: The Arcade Game
  - Tänzer (homebrew)
  - Venom/Spider-Man: Separation Anxiety
  - Zombies / Zombies Ate My Neighbors
* Sega CD
  - Jaguar XJ220
  - Wolfchild (EU and JP)
  - Son of Chuck (EU). The US disc crashes, but that is not related to the controller.

## Not tested yet

* Mega Drive
  - Alien Soldier
  - Gunstar Heroes
  - Mortal Kombat. There is already a third-party fix for 6-button pads: [Mortal Kombat Controller Fix by BillyTime! Games](https://romhackplaza.org/romhacks/mortal-kombat-controller-fix-genesis/) (for revision 1.1 of the game).
  - NBA Jam / NBA Jam Tournament Edition
  - Sonic the Hedgehog 2
  - Sonic the Hedgehog 3
* 32X
  - WWF Raw (no 32X available for testing)

## Community reports

These Reddit threads report problems with the RetroBit controller in specific games. Together with other community reports, they are why these games were picked for testing:

- [RetroBit controller not working with certain games](https://www.reddit.com/r/SEGAGENESIS/comments/lvnlp6/retrobit_controller_not_working_with_certain/)
- [Warning: RetroBit's Genesis controllers and how an...](https://www.reddit.com/r/SEGAGENESIS/comments/17ae2ei/warning_retrobits_genesis_controllers_and_how_an/)
- [My RetroBit Sega Genesis 6 button arcade pads...](https://www.reddit.com/r/SEGAGENESIS/comments/1j4om96/my_retrobit_sega_genesis_6_button_arcade_pads/): mentions Sonic 3.
- [Are the RetroBit wired controllers good?](https://www.reddit.com/r/SEGAGENESIS/comments/16o6wib/are_the_retrobit_wired_controllers_good/): mentions Mortal Kombat.
- [RetroBit Genesis 6 button controller PCB](https://www.reddit.com/r/SEGAGENESIS/comments/11ehbqp/retrobit_genesis_6_button_controller_pcb/): in Sonic 2, C behaves as if turbo were enabled. Jumps are short and repeat for as long as C is held, while A and B work normally. This matches the Start flicker described below, but on C.
- [RetroBit Genesis controller](https://www.reddit.com/r/SEGAGENESIS/comments/1e2z8py/retrobit_genesis_controller/): mentions an NBA game with C button problems, plus Gunstar Heroes and Alien Soldier.

Customer reviews on [Stone Age Gamer's page for the controller](https://stoneagegamer.com/6-button-controller-for-sega-genesis-officially-licensed.html) describe the same two faults: *"start button only works when it wants to and the C button doesn't seem to work at all in the normal 6 button mode. 3 button mode seems fine"*.

## Technical details

### How a Mega Drive controller is read

The controller port has a select line called **TH**. The console sets TH high or low and then reads the port, which returns one byte. A 0 bit means the button is pressed:

| TH | Bit 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|---|---|---|---|---|---|---|---|---|
| high | – | TH (1) | **C** | B | Right | Left | Down | Up |
| low | – | TH (0) | **Start** | A | 0 | 0 | Down | Up |

A 6-button controller counts how many times TH has been toggled. When a game toggles TH quickly, the 3rd and 4th TH-low reads and the 4th TH-high read return extra information. The pad resets the count if TH is left alone for about 1.5 ms:

| Read | TH high (C B ...) | TH low (Start A ...) |
|---|---|---|
| 1 | C B R L D U | Start A 0 0 D U |
| 2 | C B R L D U | Start A 0 0 D U |
| 3 | C B R L D U | Start A **0 0 0 0** ← "I'm a 6-button pad" |
| 4 | C B **MODE X Y Z** | Start A 1 1 1 1 |

On every read, bit 5 is C when TH is high and Start when TH is low. Games use different parts of this sequence. Some read only the first pair, some read all four, and some compare reads to check that the data is consistent.

### What the RetroBit does wrong

I captured the raw port reads with a homebrew input tester and found two separate problems.

**1. C is only reported on the first TH-high read.** With C held, a working controller reports C in every TH-high read. The RetroBit only reports it on the first one:

```
                 working pad   RetroBit
TH high, read 1  01011111      01011111   <- C pressed (bit 5 = 0)
TH high, read 2  01011111      01111111   <- RetroBit: C released
TH high, read 3  01011111      01111111
TH high, read 4  01011111      01111111
```

**2. Start flickers.** With Start held, the RetroBit switches Start on and off. When it's on, it shows up in all TH-low reads at once. The tester's "held" and "newly pressed" indicators both flash. To a game this looks like Start being pressed over and over again:

```
                 working pad              RetroBit
TH low, read 1   steady                   00110011 <-> 00010011
TH low, read 3   steady                   00110000 <-> 00010000
```

With C also held, Start registers much more reliably, which is why "Start + C" works as a workaround in several games. MODE, X, Y and Z are read from the 4th TH-high read, and they work fine.

### How each game is affected, and what the patches do

- **Lost Vikings:** detects the 6-button pad, then takes C, B and the D-pad from a later TH-high read, where the RetroBit never reports C. The patch also saves the first TH-high read and merges the two, so a button counts as pressed if either read shows it.
- **Phantom 2040:** reads all four pairs each frame. If pair 1 and pair 2 differ, it throws the whole frame away and reports nothing pressed. Holding C on the RetroBit made pair 1 and pair 2 differ, so every input disappeared for as long as C was held. If you were moving, this looked like a double-tap and toggled running. The patch:
  - ignores bit 5 (C/Start) in that comparison,
  - counts C and Start as pressed if they show up in any of the reads,
  - keeps Start held for 15 frames after it was last seen, to smooth over the flicker,
  - maps MODE to Start.
- **Mega-CD BIOS and NHL '94:** read the pad as a 3-button controller, so they only ever see the flickering Start, and MODE isn't read at all. The patches add the extra TH toggles of a 6-button read. Then MODE, from the 4th TH-high read, counts as Start, and Start is also accepted from later TH-low reads. With a 3-button controller connected, the patches check for the "6-button pad" signature first, so Right is never mistaken for MODE.
  - NHL '94 had no free space in its code. The new controller routine replaces the routine for EA's 4 Way Play adapter, which is why the patched game doesn't support that adapter.
