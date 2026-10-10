# TH probe: controller timing test ROM

A small Mega Drive test ROM that measures how quickly a controller responds when the console changes the TH select line. It was used to find the cause of the RetroBit problems.

## What it does

For each of 10 delays (0, 1, 2, 4, 8, 16, 32, 64, 128 and 256 NOPs after the TH write, about 0–135 µs), it performs a full 6-button read on port 1 and stores all 9 reads:

```
H1 (TH idle high), L1, H2, L2, H3, L3, H4, L4, H5
```

Before each delay it waits more than 2 ms, so a 6-button pad's counter resets.

The screen shows two tables:

- **Top table:** how many of the last 16 rounds had bit 5 = 0 in each read. Bit 5 is C on the TH-high reads and Start on the TH-low reads. `10` (hex) means every time and `00` means never.
- **Bottom table:** the raw byte of each read from the last round.

Hold C, then Start, then both, and compare the rows. A controller that responds fast enough shows the same result in every row, including 0 NOPs.

## Files

- `thprobe.bin`: the ROM. Run it on real hardware (flash cart) with the controller in port 1.
- `thprobe.s`: assembly source (Motorola syntax).
- `gen.py`: generates `thprobe.s`, including the font and the unrolled test code.

## Building

Assemble with [vasm](http://sun.hasenbraten.de/vasm/), built with `make CPU=m68k SYNTAX=mot`:

```
python3 gen.py
vasmm68k_mot -Fbin -m68000 -no-opt -o thprobe.bin thprobe.s
```
