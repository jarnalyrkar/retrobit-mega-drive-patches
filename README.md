These are fixes for the 9-pin version of the RetroBit controller ([Genesis](https://retro-bit.com/controllers/genesis/#console) or [Mega Drive](https://retro-bit.com/controllers/mega-drive/#console)).

These are **software fixes for a hardware shortcoming in Retro-Bit's controller**. The controller responds too slowly to the console's select signal, so some games read C and Start before the controller has updated them (details in [Technical details](#technical-details)). The patches change the games so they wait long enough. They don't change the controller, and a controller that follows the original Sega timing doesn't need them.

The controller tested here has no model number on the controller itself. The box says "SEGA MEGA DRIVE" (original logo), "6 Button Arcade Pad" and "BLACK for Mega Drive 1 and 2", and has **RET00123** printed above the barcode.

**Retro-Bit:** see [A note for Retro-Bit](#a-note-for-retro-bit) at the bottom.

> **Disclaimer:** the analysis, the patches, the tools and the test ROM in this repository were coded by AI (Claude, by Anthropic), but tested on actual hardware. Every patch listed under "Fixed" was confirmed working on a real console (a Mega Drive with a Mega EverDrive PRO and the RetroBit controller described above) before being added. Use them at your own risk, and keep your original files.

## Fixed

| Game | What the patch fixes |
|---|---|
| Lost Vikings | C doesn't work, and Start only works together with C. |
| Phantom 2040 | C (jump) and Start don't work, so you can't reach the pause menu to set punch on A. |
| Mega-CD / Sega CD BIOS | The BIOS screen needs Start + C to get past. |
| NHL '94 (Sega CD) | "Press Start" screens sometimes need Start + C. |
| Sonic the Hedgehog 2 | C doesn't work, and Start pauses and unpauses on its own. |
| Sonic the Hedgehog 3 | Same as Sonic 2. |
| Gunstar Heroes | C doesn't work. |
| Alien Soldier | C doesn't work. |
| Mortal Kombat | The controller isn't recognised, so every button does a high kick and Start (block) only works together with C. With this patch, all six buttons work as on an official 6-button pad. |
| NBA Jam / NBA Jam Tournament Edition | You can't start a game (Start and Start + C don't work), and C (pass) doesn't work. |

All patches are "timing fixes", which make the game wait long enough for the RetroBit to respond. See [The underlying cause](#the-underlying-cause-the-retrobit-responds-too-slowly-to-th).

## Patch files

Apply the patches with any IPS patcher, e.g. [Floating IPS](https://www.romhacking.net/utilities/1040/) or [Rom Patcher JS](https://www.marcrobledo.com/RomPatcher.js/). They only work on the exact files below. Check the CRC32 of your file before patching.

| Patch | Apply to | Size | CRC32 |
|---|---|---|---|
| `Lost Vikings, The (Europe) (En,Fr,De) RetroBit timing fix.ips` | Lost Vikings, The (Europe) (En,Fr,De) | 1 MB | `1F14EFC6` |
| `Phantom 2040 (4) [!] RetroBit timing fix.ips` | Phantom 2040 (USA) | 2 MB | `FB36E1F3` |
| `Phantom 2040 (8) RetroBit timing fix.ips` | Phantom 2040 (Europe) | 2 MB | `B024882E` |
| `mcd-eu BIOS RetroBit timing fix.ips` | Mega-CD (Europe) Model 1 BIOS v1.00 | 128 KB | `529AC15A` |
| `mcd-us BIOS RetroBit timing fix.ips` | Sega CD (USA) Model 1 BIOS v1.10 | 128 KB | `C6D10268` |
| `mcd-jp BIOS RetroBit timing fix.ips` | Mega-CD (Japan) Model 1 BIOS v1.00p | 128 KB | `9D2DA8F2` |
| `NHL '94 (USA) (Track 01) RetroBit timing fix.ips` | `NHL '94 (USA) (Track 01).bin` from the cue/bin set | 209,363,280 bytes | `BB13C98D` |
| `Sonic the Hedgehog 2 (JUE) [!] RetroBit timing fix.ips` | Sonic the Hedgehog 2 (World) | 1 MB | `7B905383` |
| `Sonic the Hedgehog 3 (U) [!] RetroBit timing fix.ips` | Sonic the Hedgehog 3 (USA) | 2 MB | `9BC192CE` |
| `Sonic the Hedgehog 3 (E) [converted from SMD] RetroBit timing fix.ips` | Sonic the Hedgehog 3 (Europe), plain ROM format (see below) | 2 MB | `6A632503` |
| `Gunstar Heroes (E) [!] RetroBit timing fix.ips` | Gunstar Heroes (Europe) | 1 MB | `866ED9D0` |
| `Gunstar Heroes (U) [!] RetroBit timing fix.ips` | Gunstar Heroes (USA) | 1 MB | `B813CF0D` |
| `Alien Soldier (A) [!] RetroBit timing fix.ips` | Alien Soldier (Europe/Japan) | 2 MB | `0496E06C` |
| `Mortal Kombat (JUE) (REV 00) [!] RetroBit timing fix.ips` | Mortal Kombat (World), revision 00 | 2 MB | `1AA3A207` |
| `Mortal Kombat (JUE) (REV 01) (prototype) [c][!] RetroBit timing fix.ips` | Mortal Kombat (World), revision 01 (v1.1) | 2 MB | `33F19AB6` |
| `NBA Jam (EU) (REV 01) [!] RetroBit timing fix.ips` | NBA Jam (USA/Europe), revision 01 | 2 MB | `EB8360E6` |
| `NBA Jam Tournament Edition (JUE) (REV 01) [!] RetroBit timing fix.ips` | NBA Jam Tournament Edition (World), revision 01 | 3 MB | `6E25EBF0` |

- **BIOS:** on the Mega EverDrive PRO, the patched files replace `mcd-eu.BIN`, `mcd-us.BIN` and `mcd-jp.BIN` in `MEGA/bios/` on the SD card. Keep a backup of the originals.
- **Sonic the Hedgehog 3 (Europe):** some dumps are in the old interleaved SMD format, with a 512-byte header. The patch is for the plain (de-interleaved) ROM. Convert an SMD file first, for example with a ROM converter tool.
- **NHL '94:** patch only Track 01 and keep the other tracks and the `.cue` file as they are. The patch also updates the CD sector checksums (EDC/ECC) for the changed sectors.

### Using the patches with the Mega EverDrive PRO's IPS auto-patcher

You don't have to create patched ROM files. The Mega EverDrive PRO has a built-in IPS auto-patcher (OS v4.01 and later). From the EverDrive manual:

- The patch is applied only in the cartridge RAM when the game is loaded. The ROM file on the SD card stays unchanged.
- The `.ips` file must be **in the same folder as the ROM file**, and its **file name must match the ROM file name**. For example, `Gunstar Heroes (E) [!].ips` next to `Gunstar Heroes (E) [!].bin`.

The patch files in this repository are named after the original ROM plus "RetroBit timing fix", so rename them to match your ROM file before putting them next to it. The BIOS patches are the exception: the EverDrive loads the BIOS files from `MEGA/bios/` directly, so patch those files themselves.

## Tested, no issues found

These games showed no problems with the wired 6-button controller described at the top (box code RET00123). They have **not** been tested with other Retro-Bit controllers, such as the wireless version or the Big 6, which may behave differently and could still have problems in these games.

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

### The underlying cause: the RetroBit responds too slowly to TH

C and Start share the same pin (pin 9, TR). The controller has to switch that pin between C and Start every time the console changes TH. To measure how fast the RetroBit does this, I wrote a small test ROM ([probe/](probe/), with source). It changes TH, waits a set number of NOP instructions, reads the port, and counts how often bit 5 reads as pressed. Each delay is tested 16 times:

| Delay after TH change | Holding C: TH-high reads 2–5 | Holding Start: TH-low reads 1–4 |
|---|---|---|
| 0, 1 or 2 NOPs (up to ~1 µs) | 0 of 16 (C missing) | 0 of 16 (Start missing) |
| 4 NOPs (~2 µs) or more | 16 of 16 | 16 of 16 |

The first TH-high read, taken before any TH change, always shows C correctly. Holding C and Start together reads as pressed at every delay, since both buttons pull the same pin low.

So the RetroBit needs somewhere between about 1 and 2 µs after a TH change before its outputs are valid. Many games read after only 2 NOPs (about 1 µs at the Mega Drive's 7.6 MHz). Depending on the exact timing of each read, the result is C missing completely or Start flickering. Given enough time, the RetroBit reports every button correctly and Start doesn't flicker at all.

### How each game is affected, and what the patches do

- **Lost Vikings:** detects the 6-button pad, then takes C, B and the D-pad from a later TH-high read, which comes only about 0.5 µs after a TH change. The RetroBit never reports C there, and Start is unreliable.
- **Phantom 2040:** reads all four pairs each frame. If pair 1 and pair 2 differ, it throws the whole frame away and reports nothing pressed. Holding C on the RetroBit made pair 1 and pair 2 differ, so every input disappeared for as long as C was held. If you were moving, this looked like a double-tap and toggled running.
- Both now use the same timing fix as the games below, applied to the original ROMs. Earlier versions of these two patches worked around the symptoms instead (merging reads, a Start hold, and MODE as Start in Phantom 2040). They are replaced by the timing fixes, which make the regular Start button work too.
- **Lost Vikings, Phantom 2040, Sonic 2/3, Gunstar Heroes, Alien Soldier, Mortal Kombat, NBA Jam and NBA Jam TE (timing fixes):** these games wait only about 0.5–1 µs between changing TH and reading the port. The patches make every such read wait about 4 µs:
  - Where the ROM has unused space, each "write TH + next instruction" (6 bytes) is replaced with a call to a small routine. That routine does the same two instructions, waits, and returns.
  - Sonic 2 and 3 have no free space, so their controller routine is rearranged in place instead. It reads the TH-high half first, while TH is still idle and valid, then switches TH low and does its bit-shuffling while the pad settles.
  - Mortal Kombat's 6-button detection used to fail with the RetroBit, so the game didn't recognise the controller and every button did a high kick. Both the detection and the 6-button reader are fixed.
  - There is also a separate [Mortal Kombat Controller Fix by BillyTime! Games](https://romhackplaza.org/romhacks/mortal-kombat-controller-fix-genesis/) for third-party 6-button pads (revision 1.1). It hasn't been tested with the RetroBit here.
- **Mega-CD BIOS and NHL '94:** read the pad as a 3-button controller, with only about 1 µs between changing TH and reading. Neither has usable free space, so the controller routine is rearranged in place, as in Sonic 2/3. It reads the idle TH-high half first, then switches TH low and waits about 4.5 µs before the second read, using a slow 2-byte shift instruction on a register that's overwritten afterwards. The routines stay the same size, so nothing else in the BIOS or game moves, and NHL '94 keeps its support for EA's 4 Way Play adapter.
  - Earlier versions of these two patches added a 6-button read so MODE worked as Start. They are replaced by the timing fixes, which make the regular Start button work.

## A note for Retro-Bit

This is meant as friendly feedback. The controller is still on sale, and the problem can be fixed, so here's what I found and what would fix it in future production runs or firmware.

**The problem:** after the console changes the TH select line (pin 7), the controller (box code RET00123, "6 Button Arcade Pad") takes roughly 1–2 µs to update its outputs, in particular pin 9 (TR, the shared C/Start line). Many licensed games read the port only about 1 µs after changing TH. Those reads get stale values, so C doesn't register and Start flickers. Pressing C and Start together works around it, because then pin 9 is low in both TH states. The full measurements are in [The underlying cause](#the-underlying-cause-the-retrobit-responds-too-slowly-to-th) above.

**Suggested fixes**, in order of robustness:

1. **Switch the outputs in hardware.** The original 3-button pads drive pins 1–4, 6 and 9 through a simple 2:1 multiplexer (a 74HC157-type chip) selected directly by TH. That switches in nanoseconds, whatever the microcontroller is doing. The microcontroller then only has to keep the button states on the multiplexer's inputs updated, and handle the 6-button extra cycles.
2. **If the outputs must come from the microcontroller:** prepare both output states (TH high and TH low) in advance, and react to the TH edge with a pin-change or edge interrupt, or a very tight loop, so the port is rewritten within a few hundred nanoseconds. Avoid scanning buttons, debouncing or any other work between seeing the TH edge and updating the outputs.
3. **6-button protocol:** keep the standard behaviour of resetting the TH counter after about 1.5 ms without TH changes, and make sure the TH-high and TH-low states in every cycle of the sequence are valid as quickly as on cycle 1.

**How to test it:** the [test ROM in probe/](probe/) does this. Read the port immediately after changing TH (0 NOPs), as well as after 1 and 2 NOPs, and check that C (TH high) and Start (TH low) read correctly on every read of the 6-button sequence. Sonic the Hedgehog 2 and 3, Gunstar Heroes, Alien Soldier, Mortal Kombat and NBA Jam are good real-game tests. With the current controller, all of them have problems with C, Start or both.

If existing controllers can be updated, a firmware fix would help everyone who already owns one.
