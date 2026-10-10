# Untested timing patches

These patches were generated automatically by scanning the GoodGen Mega Drive romset for controller reads that come too soon after a TH change. That's the cause of the RetroBit's C and Start problems, explained in the [main README](../README.md#technical-details).

**They have not been tested on hardware, but they should work.** They use the same two methods as the verified patches in the main folder:

- **In place:** the standard Sega controller routine is rearranged in the same space. This is the method used for Sonic 2/3, the Mega-CD BIOS and NHL '94.
- **Wait routines:** each short read jumps to a small routine in unused padding at the end of the ROM, which waits about 4 µs. This is the method used for Gunstar Heroes, Mortal Kombat, NBA Jam and others.

Notes:

- A game being listed only means its code reads the controller faster than the RetroBit can respond. Many of these games may work fine without a patch, for example when the affected read doesn't involve C or Start.
- Each patch is named exactly like the ROM it belongs to (GoodGen naming), so it can be used directly with the Mega EverDrive PRO's IPS auto-patcher: put it next to the ROM, with the same name. Check the CRC32 before patching.
- Some patches leave a few reads alone, because no controller port address was found nearby. Those are noted in the table.
- Three ROMs (D&D – Warriors of the Eternal Sun, Sonic the Hedgehog 3 (E) and Sub-Terrania) are SMD-interleaved in the romset. Their patches are for the plain (de-interleaved) ROM, and the CRC32 is for that version.
- `NHL Hockey '94 (Europe) (Track 01) RetroBit timing fix.ips` is for the Sega CD game (Redump cue/bin, Track 01 CRC32 `09AC07A1`). It is the same in-place fix as the verified NHL '94 (USA) patch, at the same offsets, but hasn't been tested with the controller on the Europe disc.
- If a patch causes a problem, please report it, and use the original ROM in the meantime. If you test one and it works, it can be moved to the verified list.

## Patches (897)

| ROM | Size | CRC32 | Fix | Note |
|---|---|---|---|---|
| 16 Ton (J) [!] | 256 KB | `537F04B6` | standard routine rearranged in place |  |
| 688 Attack Sub (U) [!] | 1 MB | `F2C58BF7` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| 777 Casino (Unl) [c] | 1 MB | `42DC03E4` | standard routine rearranged in place |  |
| A Ressha de Gyoukou MD (J) [!] | 512 KB | `3D45DE4F` | 1 read(s) with a wait routine |  |
| Aah! Harimanada (J) | 2 MB | `065F6021` | 2 read(s) with a wait routine |  |
| Abrams Battle Tanks (U) | 512 KB | `A3FA9B38` | 2 read(s) with a wait routine |  |
| Activator Command Demo 30 Hz (JUE) [c][!] | 256 KB | `4CD5674C` | 2 read(s) with a wait routine |  |
| Activator Command Demo 60 Hz (JUE) [c][!] | 256 KB | `6A9E4D2C` | 2 read(s) with a wait routine |  |
| Addams Family, The (UE) [!] | 1 MB | `71F58614` | 2 read(s) with a wait routine |  |
| Advanced Daisenryaku (J) | 1 MB | `50625642` | standard routine rearranged in place |  |
| Adventures of Batman and Robin, The (E) | 2 MB | `355E8C39` | standard routine rearranged in place |  |
| Adventures of Batman and Robin, The (JU) [!] | 2 MB | `0CAAA4AC` | standard routine rearranged in place |  |
| Aero Blasters (JU) [!] | 512 KB | `A00DA987` | standard routine rearranged in place |  |
| Aero the Acro-Bat (U) [c][!] | 1 MB | `A3A7A8B5` | 2 read(s) with a wait routine |  |
| Aero the Acro-Bat 2 (E) | 2 MB | `A451F9A1` | 2 read(s) with a wait routine |  |
| Aero the Acro-Bat 2 (U) [!] | 2 MB | `39EB74EB` | 2 read(s) with a wait routine |  |
| Aero The Acrobat 2 (U) | 2 MB | `AAA351C0` | 2 read(s) with a wait routine |  |
| Aerobiz (U) [!] | 1 MB | `CFAA9BCE` | standard routine rearranged in place |  |
| Aerobiz Supersonic (U) [!] | 1 MB | `9377F1B5` | 5 read(s) with a wait routine |  |
| After Burner II (J) | 512 KB | `4FF37E66` | standard routine rearranged in place |  |
| After Burner II (U) [!] | 512 KB | `CCAFE00E` | standard routine rearranged in place |  |
| Air Busters (U) [c][!] | 512 KB | `F3D65BAA` | standard routine rearranged in place |  |
| Air Diver (J) | 512 KB | `9E2D5B91` | standard routine rearranged in place |  |
| Air Diver (U) [!] | 512 KB | `2041885E` | standard routine rearranged in place |  |
| Air Management II - Kouku Ou wo Mezase (J) | 1 MB | `4582817B` | standard routine rearranged in place |  |
| Aleste - Full Metal Fighter Ellinor (J) [!] | 512 KB | `8FDE18AB` | standard routine rearranged in place |  |
| Alex Kid - Cheongongmaseong (K) | 256 KB | `5B0678FB` | 3 read(s) with a wait routine |  |
| Alex Kidd in the Enchanted Castle (E) [!] | 256 KB | `C3A52529` | 3 read(s) with a wait routine |  |
| Alex Kidd in the Enchanted Castle (U) [!] | 256 KB | `47DBA0AC` | 3 read(s) with a wait routine |  |
| Alien Soldier (A) [!] | 2 MB | `0496E06C` | 4 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Alien Soldier (B) [c] | 2 MB | `A8E93A2A` | 4 read(s) with a wait routine |  |
| Alien Soldier (U) | 2 MB | `679C63EB` | 4 read(s) with a wait routine |  |
| Alien Storm (JUE) [!] | 512 KB | `F5AC8DE5` | 2 read(s) with a wait routine |  |
| Altered Beast (JU) (REV 00) [c][!] | 512 KB | `1B7C96C0` | 3 read(s) with a wait routine |  |
| Altered Beast (JU) (REV 01) [!] | 512 KB | `B2233E87` | 3 read(s) with a wait routine |  |
| Altered Beast (JU) (REV 02) [!] | 512 KB | `154D59BB` | 3 read(s) with a wait routine |  |
| Ambition of Caesar (J) | 1 MB | `69796E93` | 2 read(s) with a wait routine |  |
| American Gladiators (U) [!] | 1 MB | `9952FA85` | 2 read(s) with a wait routine |  |
| Andre Agassi Tennis (JE) (REV 01) [c][!] | 512 KB | `224256C7` | 2 read(s) with a wait routine |  |
| Andre Agassi Tennis (JU) (REV 00) [!] | 512 KB | `E755DD51` | 2 read(s) with a wait routine |  |
| Andre Agassi Tennis (U) | 512 KB | `5A8032A6` | 2 read(s) with a wait routine |  |
| Animaniacs (E) | 1 MB | `92B6F255` | 2 read(s) with a wait routine |  |
| Animaniacs (UJ) [!] | 1 MB | `86224D86` | 2 read(s) with a wait routine |  |
| Aoki Ookami to Shiroki Meshika - Genchou Hishi (J) [!] | 1280 KB | `10BE1D93` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Arch Rivals (UE) [!] | 512 KB | `E389D7E7` | 4 read(s) with a wait routine |  |
| Arcus Odyssey (J) | 1 MB | `41C5FB4F` | standard routine rearranged in place |  |
| Arcus Odyssey (U) [!] | 1 MB | `BC4D9B20` | standard routine rearranged in place |  |
| Arrow Flash (JUE) [!] | 512 KB | `4D89E66B` | standard routine rearranged in place |  |
| Art of Fighting (E) [!] | 2 MB | `9970C422` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Art of Fighting (J) | 2 MB | `054CF5F6` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Art of Fighting (U) [!] | 2 MB | `C9A57E07` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Assault Suits Leynoss (J) [!] | 512 KB | `81A2C800` | standard routine rearranged in place |  |
| Atomic Robo Kid (J) [c] | 512 KB | `E833067E` | standard routine rearranged in place |  |
| Atomic Robo Kid (U) [c][!] | 512 KB | `7CD8169E` | standard routine rearranged in place |  |
| Atomic Runner (E) [!] | 1 MB | `B3C05418` | standard routine rearranged in place |  |
| Atomic Runner (J) [R-USA][!] | 1 MB | `0677C210` | standard routine rearranged in place |  |
| ATP Tour Championship Tennis (E) | 2 MB | `1A3DA8C5` | 5 read(s) with a wait routine |  |
| ATP Tour Championship Tennis (U) [!] | 2 MB | `8C822884` | 5 read(s) with a wait routine |  |
| atp_tour_tennis | 2 MB | `3E116F38` | 5 read(s) with a wait routine |  |
| Australian Rugby League (E) [!] | 2 MB | `AC5BC26A` | 7 read(s) with a wait routine |  |
| Ayrton Senna's Super Monaco GP II (JE) [!] | 1 MB | `60AF0F76` | 2 read(s) with a wait routine |  |
| Ayrton Senna's Super Monaco GP II (U) [!] | 1 MB | `EAC8DED6` | 2 read(s) with a wait routine |  |
| Baby's Day Out (U) | 1 MB | `B2E7CC49` | 2 read(s) with a wait routine |  |
| bad_omen | 512 KB | `20F628D9` | standard routine rearranged in place |  |
| Ballz (JUE) [!] | 2 MB | `B362B705` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Bare Knuckle III (J) [!] | 3 MB | `5D09236F` | 7 read(s) with a wait routine |  |
| Barkley Shut Up and Jam 2 (JUE) [!] | 2 MB | `321BB6BD` | 10 read(s) with a wait routine |  |
| Barkley Shut Up and Jam! (JUE) [!] | 1 MB | `63FBF497` | 10 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| barkley_shut_up_and_jam | 1 MB | `D34C435F` | 10 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Barver Battle Saga - The Space Fighter (Chinese) | 2 MB | `D37A37C6` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Batman (E) | 512 KB | `61C60C35` | standard routine rearranged in place |  |
| Batman (J) [!] | 512 KB | `D7B4FEBF` | standard routine rearranged in place |  |
| Batman (UE) [!] | 512 KB | `017410AE` | standard routine rearranged in place |  |
| Battle Mania 2 - TS Vintage (J) [c][!] | 1 MB | `312FA0F2` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Battle Squadron (U) [!] | 512 KB | `0FEAA8BF` | 2 read(s) with a wait routine |  |
| battle_toads | 512 KB | `6CDBFFCD` | standard routine rearranged in place |  |
| Battlemaster (JUE) [c][!] | 512 KB | `FD2B35E3` | 2 read(s) with a wait routine |  |
| Battletoads (JUE) [!] | 512 KB | `D10E103A` | standard routine rearranged in place |  |
| Battletoads and Double Dragon (U) [c][!] | 1 MB | `8239DD17` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Beast Warrior (J) | 1 MB | `4646C694` | standard routine rearranged in place |  |
| Beast Wrestler (U) [!] | 1 MB | `0CA5BB64` | standard routine rearranged in place |  |
| Best of the best Championship Karate (U) | 1536 KB | `7E27C11A` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Bill Walsh College Football '95 (U) | 2 MB | `F7ECD5CD` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Bill Walsh College Football '95 (U) [!] | 2 MB | `A582F45A` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Bill Walsh College Football (UEJ) [c][!] | 1 MB | `3ED83362` | 2 read(s) with a wait routine |  |
| Bioship Paladin (JU) [c][!] | 1 MB | `C511E8D2` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Bishoujo Senshi Sailor Moon (J) [!] | 2 MB | `5E246938` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Body Count (E) [!] | 1 MB | `3575A030` | 2 read(s) with a wait routine |  |
| Bonanza Brothers (JUE) (REV 00) [!] | 512 KB | `ADF6476C` | standard routine rearranged in place |  |
| Bonanza Brothers (JUE) (REV 01) | 512 KB | `C6AAC589` | standard routine rearranged in place |  |
| Bonanza Brothers (UE) (REV 00) [!] | 512 KB | `20D1AD4C` | standard routine rearranged in place |  |
| Boogie Woogie Bowling (J) | 512 KB | `CCF52828` | 4 read(s) with a wait routine |  |
| Brian Lara Cricket (E) (Jun 1995) [c][!] | 1 MB | `408CF5C3` | standard routine rearranged in place |  |
| Brian Lara Cricket (JE) (Mar 1995) [c] | 1 MB | `90F5C2B7` | standard routine rearranged in place |  |
| Brian Lara Cricket 96 (E) (Apr 1996) [c] | 1 MB | `FE52F7E1` | standard routine rearranged in place |  |
| Brian Lara Cricket 96 (E) (Mar 1996) [c][!] | 1 MB | `FA3024AF` | standard routine rearranged in place |  |
| brian_lara_cricket | 1 MB | `2042757F` | standard routine rearranged in place |  |
| C_POOL | 1 MB | `526F0075` | standard routine rearranged in place |  |
| Cadash (U) [c][!] | 512 KB | `13BDF374` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Caliber Fifty (J) [!] | 1 MB | `44F4FA05` | standard routine rearranged in place |  |
| Capt'n Havoc (E) [!] | 1 MB | `76E6D20D` | standard routine rearranged in place |  |
| Captain America and the Avengers (E) | 1 MB | `43225612` | standard routine rearranged in place |  |
| Captain America and the Avengers (J) [!] | 1 MB | `E0639CA2` | standard routine rearranged in place |  |
| Captain Planet and the Planeteers (U) (Dec 1992) | 512 KB | `BF2CBD3A` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Captain Planet and the Planeteers (U) (Nov 1992) [R-Eur][!] | 512 KB | `7672EFA5` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Chameleon Kid (J) [!] | 1 MB | `50217C80` | standard routine rearranged in place |  |
| Championship Bowling (U) [!] | 512 KB | `1BF92520` | 4 read(s) with a wait routine |  |
| Championship Pool (U) [!] | 1 MB | `253512CF` | standard routine rearranged in place |  |
| Championship Pro Am (U) [c][!] | 256 KB | `B496DE28` | 2 read(s) with a wait routine |  |
| Chase HQ 2 (JUE) [!] | 512 KB | `F39E4BF2` | standard routine rearranged in place |  |
| Chelnov (J) | 1 MB | `B2FE74D8` | standard routine rearranged in place |  |
| Chester Cheetah (U) [c][!] | 1 MB | `250E3EC3` | standard routine rearranged in place |  |
| Chester Cheetah 2 - Wild Wild Quest (U) [!] | 1 MB | `B97B735D` | 2 read(s) with a wait routine |  |
| Chi Chi's Pro Challenge (U) [!] | 1 MB | `9C3973A4` | 2 read(s) with a wait routine |  |
| Chiki Chiki Boys (J) [!] | 1 MB | `06918C17` | standard routine rearranged in place |  |
| Chiki Chiki Boys (U) [!] | 1 MB | `813A7D62` | standard routine rearranged in place |  |
| chiki_chiki_boys_jap | 1 MB | `B6263BDF` | standard routine rearranged in place |  |
| Chinese Chess (Unl) | 512 KB | `475215A0` | 4 read(s) with a wait routine |  |
| Chou Yakyuu Miracle Nine (1) [!] | 2 MB | `6D8C2206` | 7 read(s) with a wait routine |  |
| Chuck's Excellent Art Tool Animator (JUE) [c][!] | 384 KB | `6360EE58` | 3 read(s) with a wait routine |  |
| Coach K College Basketball (U) [!] | 2 MB | `67C309C6` | 7 read(s) with a wait routine |  |
| College Football USA 96 (4) [!] | 2 MB | `B9075385` | 2 read(s) with a wait routine |  |
| College Football USA 97 (4) [!] | 2 MB | `2EBB90A3` | 2 read(s) with a wait routine |  |
| College Football's National Championship (U) [!] | 2 MB | `172C5DBB` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| College Football's National Championship 2 (F) [!] | 2 MB | `65B64413` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Columns (JU) (REV 00) | 128 KB | `03163D7A` | 3 read(s) with a wait routine |  |
| Columns (JU) (REV 01) [!] | 128 KB | `D783C244` | 3 read(s) with a wait routine |  |
| Columns 3 - Revenge of Columns (J) | 512 KB | `CD07462F` | 1 read(s) with a wait routine |  |
| Columns 3 - Revenge of Columns (U) [!] | 512 KB | `DC678F6D` | 1 read(s) with a wait routine |  |
| Comix Zone (1) [!] | 2 MB | `7A6027B8` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Comix Zone (4) [!] | 2 MB | `17DA0354` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Comix Zone (A) | 2 MB | `1318E923` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Conquering the World 3 (Chinese) | 2 MB | `B23C4166` | standard routine rearranged in place |  |
| Conquering the World 3 (Chinese-Simple) | 2 MB | `EA57B668` | standard routine rearranged in place |  |
| Crack Down (J) [!] | 512 KB | `538AAA5D` | 2 read(s) with a wait routine |  |
| Crack Down (UE) [!] | 512 KB | `B9CE9051` | 2 read(s) with a wait routine |  |
| Crayon Shin-Chan (J) | 2 MB | `97FC42D2` | 5 read(s) with a wait routine |  |
| CrossFire (J) [c][!] | 512 KB | `CC73F3A9` | standard routine rearranged in place |  |
| Crude Busters (J) | 1 MB | `BF5529CB` | standard routine rearranged in place |  |
| Crue Ball (U) [!] | 512 KB | `4B195FC0` | 4 read(s) with a wait routine |  |
| Crusader of Centy (U) [!] | 2 MB | `41858F6F` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Curse (J) [!] | 512 KB | `A4FBF9A9` | 2 read(s) with a wait routine |  |
| Cutie Suzuki no Ringside Angel (JU) [!] | 512 KB | `13795DCA` | standard routine rearranged in place |  |
| cyberball | 512 KB | `CBC7E161` | 2 read(s) with a wait routine |  |
| CyberBall (JU) [!] | 512 KB | `76120E96` | 2 read(s) with a wait routine |  |
| D&D - Warriors of the Eternal Sun (U) [!] | 1 MB | `AF4A9CD7` | standard routine rearranged in place | For the de-interleaved (non-SMD) ROM |
| Dai Makai-Mura (J) (REV 00) [!] | 640 KB | `5659F379` | standard routine rearranged in place |  |
| Dai Makai-Mura (J) (REV 01) | 640 KB | `F6E606B6` | standard routine rearranged in place |  |
| Daikoukai Jidai II (J) | 2 MB | `E040F0DA` | 5 read(s) with a wait routine |  |
| Dangerous Seed (J) [!] | 512 KB | `A2990031` | standard routine rearranged in place |  |
| Darwin 4081 (J) [!] | 512 KB | `7A33B0CB` | standard routine rearranged in place |  |
| Dashin' Desperadoes (U) [!] | 1 MB | `DCB76FB7` | standard routine rearranged in place |  |
| Daze Before Christmas, The (E) [!] | 2 MB | `B95E25C9` | 4 read(s) with a wait routine |  |
| Decap Attack (UE) [!] | 512 KB | `73DC0DD8` | 2 read(s) with a wait routine |  |
| Decap Attack (UJ) | 512 KB | `AB177FAD` | standard routine rearranged in place |  |
| Desert Demolition (UJE) [!] | 1 MB | `C287343D` | 20 read(s) with a wait routine |  |
| Devil's Course 3-D Golf (J) [!] | 1536 KB | `BD090C67` | 2 read(s) with a wait routine |  |
| Devilish (U) [c][!] | 512 KB | `D3F300AC` | standard routine rearranged in place |  |
| Dick Tracy (JUE) [c][!] | 512 KB | `EF887533` | standard routine rearranged in place |  |
| Dino Land (JU) [!] | 512 KB | `5FE351B8` | standard routine rearranged in place |  |
| dino_land | 512 KB | `E236BE4F` | standard routine rearranged in place |  |
| Disney Collection - Castle of Illusion & Quackshot (F) [!] | 1 MB | `ADFDE883` | 5 read(s) with a wait routine |  |
| Divine Sealing (JU) [c][!] | 1 MB | `CA72973C` | standard routine rearranged in place |  |
| Dodge Ball - Kuy Kid (J) | 512 KB | `630F07C6` | standard routine rearranged in place |  |
| Doki Doki Penguin Land (J) [!] | 256 KB | `0053BFD6` | standard routine rearranged in place |  |
| Double Dragon 2 (J) [!] | 512 KB | `A8BFDBD6` | 2 read(s) with a wait routine |  |
| Double Dragon V - The Shadow Falls (U) [!] | 3 MB | `27E59E35` | 2 read(s) with a wait routine |  |
| Double Dribble - Playoff Edition (U) [!] | 2 MB | `8352B1D0` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Dr. Robotnik's Mean Bean Machine (U) [!] | 1 MB | `C7CA517F` | 4 read(s) with a wait routine |  |
| Dragon - The Bruce Lee Story (E) | 2 MB | `FDEED51D` | 5 read(s) with a wait routine |  |
| Dragon - The Bruce Lee Story (U) [!] | 2 MB | `EFE850E5` | 5 read(s) with a wait routine |  |
| Dragon Ball Z (E) (Fre) | 2 MB | `F035C737` | standard routine rearranged in place; 5 read(s) with a wait routine |  |
| Dragon Ball Z - Buu Yuu Retsuden (J) [!] | 2 MB | `AF8F3371` | standard routine rearranged in place; 5 read(s) with a wait routine |  |
| Dragon Slayer 2 - Legend of Heroes (B) [!] | 2 MB | `46924DC3` | 1 read(s) with a wait routine |  |
| Dragon's Eye - Shanghai 3 (J) | 256 KB | `81F0C3CF` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Draxos (J) | 1 MB | `1EA07AF2` | 2 read(s) with a wait routine |  |
| Duke Nukem 3D (F) | 4 MB | `83BA0C92` | 3 read(s) with a wait routine |  |
| duke_nukem3d | 4 MB | `57355FE1` | 3 read(s) with a wait routine |  |
| Dune - Der Kampf um den Wuestenplaneten (E) (Ger) | 1 MB | `39790728` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Dune - The Battle for Arrakis (E) | 1 MB | `B58AE71D` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Dune - The Building of a Dynasty (U) [!] | 1 MB | `4DEA40BA` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Dyna Brothers 2 (J) [!] | 2 MB | `47E0A64E` | 6 read(s) with a wait routine |  |
| Dynamite Duke (JU) [!] | 512 KB | `39D01C8C` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Dynamite Headdy (J) [c][!] | 2 MB | `D03CDB53` | 2 read(s) with a wait routine |  |
| Dynamite Headdy (UE) [c][!] | 2 MB | `3DFEEB77` | 2 read(s) with a wait routine |  |
| dynamite_duke | 512 KB | `4B86FE9D` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| EA Sports 2-in-1 Pack (E) [!] | 1 MB | `A0B54CBC` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Earnest Evans (U) [!] | 1 MB | `A243816D` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| El Viento (J) | 1 MB | `6091C36E` | standard routine rearranged in place |  |
| El Viento (U) [!] | 1 MB | `070A1CEB` | standard routine rearranged in place |  |
| Eliminate Down (J) | 1 MB | `48467542` | standard routine rearranged in place |  |
| Empire of Steel (UE) | 1 MB | `E5517B77` | 2 read(s) with a wait routine |  |
| ESPN National League Hockey Night (U) [c][!] | 2 MB | `1D08828C` | 2 read(s) with a wait routine |  |
| ESWAT Cyber Police - City Under Siege (J) | 512 KB | `87B636A2` | standard routine rearranged in place |  |
| ESWAT Cyber Police - City Under Siege (JUE) [R-USA][!] | 512 KB | `E72F8A36` | 2 read(s) with a wait routine |  |
| Ex-Ranza (J) | 1 MB | `349BB68D` | standard routine rearranged in place; 8 read(s) with a wait routine |  |
| Exile (U) [!] | 1 MB | `1B569DC2` | standard routine rearranged in place |  |
| F-117 Night Storm (UEJ) [!] | 2 MB | `1BF67A07` | 3 read(s) with a wait routine |  |
| F-117 Stealth - Operation Night Storm (UEJ) | 2 MB | `EA6E421A` | 3 read(s) with a wait routine |  |
| F1 Circus MD (J) [!] | 512 KB | `5D30BEFB` | standard routine rearranged in place |  |
| F1 Grand Prix - Nakajima Satoru (J) [!] | 1 MB | `93BE47CF` | standard routine rearranged in place |  |
| F1 Hero MD (J) [c][!] | 1 MB | `24F87987` | standard routine rearranged in place |  |
| F1 Super License - Nakajima Satoru (J) | 1 MB | `8774BC79` | standard routine rearranged in place |  |
| F1 World Championship (E) [!] | 1 MB | `FBDD4520` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| F1 World Championship (JUE) [!] | 1 MB | `CCD73738` | 3 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Fastest 1 (J) [!] | 512 KB | `BB43F0DE` | standard routine rearranged in place; 3 read(s) with a wait routine |  |
| Fatal Fury (E) | 1536 KB | `2E730A91` | 2 read(s) with a wait routine |  |
| Fatal Fury (U) [!] | 1536 KB | `98D49170` | 2 read(s) with a wait routine |  |
| Fatal Labyrinth (JU) [!] | 128 KB | `5F0BD984` | standard routine rearranged in place |  |
| Fatman (J) [c][!] | 640 KB | `7867DA3A` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Fengshen Yingjiechuan (Chinese) | 2 MB | `6A382B60` | standard routine rearranged in place |  |
| Ferias Frustradas do Pica-Pau (Unl) | 1 MB | `91F11037` | 1 read(s) with a wait routine |  |
| Ferrari Grand Prix Challenge (U) [!] | 1 MB | `F73F6BEC` | standard routine rearranged in place |  |
| FIFA International Soccer (EUJ) [!] | 2 MB | `BDDBB763` | 3 read(s) with a wait routine |  |
| FIFA Soccer 95 (EUJ) [!] | 2 MB | `B389D036` | 7 read(s) with a wait routine |  |
| FIFA Soccer 96 (F) [!] | 2 MB | `BAD30FFA` | 7 read(s) with a wait routine |  |
| FIFA Soccer 97 Gold Edition (C) [!] | 2 MB | `A33D5803` | 7 read(s) with a wait routine |  |
| FIFA Soccer 98 - Road to the World Cup (8) [!] | 2 MB | `96947F57` | 7 read(s) with a wait routine |  |
| fifa_97 | 2 MB | `D0C9F6BC` | 7 read(s) with a wait routine |  |
| Fighting Masters (J) | 512 KB | `39BE80EC` | standard routine rearranged in place |  |
| Fighting Masters (U) [!] | 512 KB | `5F51983B` | standard routine rearranged in place |  |
| Final Fantasy (R) (Unl) | 2 MB | `CA14B36B` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Final Zone (JU) [!] | 512 KB | `731FA4A1` | standard routine rearranged in place |  |
| Fire Mustang (J) [c][!] | 512 KB | `EB7E36C3` | standard routine rearranged in place |  |
| Fire Pro Wrestling Gaiden (J) [c][!] | 512 KB | `24408C73` | standard routine rearranged in place |  |
| Flashback - The Quest for Identity (E) [!] | 1536 KB | `6F311C83` | 2 read(s) with a wait routine |  |
| Flashback - The Quest for Identity (J) | 1536 KB | `B790E3B4` | 2 read(s) with a wait routine |  |
| Flashback - The Quest for Identity (U) [!] | 1536 KB | `23A9616D` | 2 read(s) with a wait routine |  |
| Flicky (JUE) [!] | 128 KB | `4291C8AB` | standard routine rearranged in place |  |
| Flintstones, The (E) [c][!] | 512 KB | `21845D61` | 2 read(s) with a wait routine |  |
| Flintstones, The (U) [c][!] | 512 KB | `7C982C59` | 2 read(s) with a wait routine |  |
| FMLITE | 8 KB | `F9AC855D` | 1 read(s) with a wait routine |  |
| Gadget Twins (U) [!] | 1 MB | `7AE5E248` | 2 read(s) with a wait routine |  |
| Gaiares (JU) [!] | 1 MB | `5D8BF68B` | standard routine rearranged in place |  |
| Gain Ground (JU) [c][!] | 512 KB | `83E7B8AE` | standard routine rearranged in place |  |
| Galaxy Force II (J) (REV 00) | 1 MB | `CAE883C5` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Galaxy Force II (JU) (REV 01) [!] | 1 MB | `D15F5C3C` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Gambler Jiko Chuushinha - Katayama Masayuki no Mahjong Doujou (J) [!] | 512 KB | `05650B7A` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Gamtec Magicard (Unl) [c][!] | 32 KB | `1886EB34` | 2 read(s) with a wait routine |  |
| Garou Densetsu (J) [!] | 1536 KB | `BF3E3FA4` | 2 read(s) with a wait routine |  |
| Gauntlet 4 (UE) (Aug 1993) [!] | 1 MB | `3BF46DCE` | 1 read(s) with a wait routine |  |
| Gauntlet 4 (UE) (Sep 1993) | 1 MB | `F9D60510` | 1 read(s) with a wait routine |  |
| Gauntlet Arcade Version (J) | 1 MB | `F9872055` | 1 read(s) with a wait routine |  |
| GemFire (U) [!] | 1 MB | `3D36135B` | standard routine rearranged in place |  |
| General Chaos (UEJ) [!] | 1 MB | `F1ECC4DF` | 2 read(s) with a wait routine |  |
| Genghis Khan 2 (U) [!] | 1 MB | `87A281AE` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Ghost Hunter (Unl) [c] | 512 KB | `76C62A8B` | standard routine rearranged in place |  |
| Ghostbusters (JUE) (REV 00) | 512 KB | `00419DA3` | standard routine rearranged in place |  |
| Ghostbusters (JUE) (REV 01) [!] | 512 KB | `792DF93B` | standard routine rearranged in place |  |
| Ghouls 'N Ghosts (JUE) (REV 01) [!] | 640 KB | `D31BD910` | standard routine rearranged in place |  |
| Ghouls 'N Ghosts (JUE) (REV 02) [!] | 640 KB | `4F2561D5` | standard routine rearranged in place |  |
| ghouls_and_ghosts | 640 KB | `18D95E1A` | standard routine rearranged in place |  |
| Gley Lancer (J) | 1 MB | `42CF9B5B` | standard routine rearranged in place |  |
| Golden Axe (JU) (REV 00) [!] | 512 KB | `E8182B90` | 2 read(s) with a wait routine |  |
| Golden Axe (JUE) (REV 01) [!] | 512 KB | `665D7DF9` | 2 read(s) with a wait routine |  |
| Goofy's Hysterical History Tour (U) | 1 MB | `4E1CC833` | standard routine rearranged in place |  |
| Grand Slam Tennis (E) [!] | 512 KB | `8C2670DE` | standard routine rearranged in place |  |
| Grand Slam Tennis (J) | 512 KB | `30CF37D0` | standard routine rearranged in place |  |
| Growl (JUE) [!] | 512 KB | `F60EF143` | standard routine rearranged in place |  |
| Gunstar Heroes (E) [!] | 1 MB | `866ED9D0` | 4 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Gunstar Heroes (J) | 1 MB | `1CFD0383` | 4 read(s) with a wait routine |  |
| Gunstar Heroes (U) [!] | 1 MB | `B813CF0D` | 4 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Gunstar Heroes Sample (JUE) [!] | 1 MB | `6F90B502` | 4 read(s) with a wait routine |  |
| Gynoug (E) [!] | 512 KB | `03405102` | standard routine rearranged in place |  |
| Gynoug (J) [!] | 512 KB | `1B69241F` | standard routine rearranged in place |  |
| H_DUNK | 2 MB | `6E31F5D7` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Hard Drivin' (JU) [!] | 256 KB | `3225BAAF` | 1 read(s) with a wait routine |  |
| HardBall (U) [!] | 1 MB | `BD1B9A04` | 2 read(s) with a wait routine |  |
| HardBall 3 (JUE) | 2 MB | `A4F2F011` | 3 read(s) with a wait routine |  |
| HardBall 94 (JUE) [!] | 2 MB | `EA9C4878` | 3 read(s) with a wait routine |  |
| Harry Potter (R) (Unl) | 2 MB | `A184FC76` | 4 read(s) with a wait routine |  |
| Haunting, The (UEJ) [!] | 2 MB | `C9FC876D` | 2 read(s) with a wait routine |  |
| Head-On Soccer (4) [!] | 2 MB | `DCFFA327` | 11 read(s) with a wait routine |  |
| Head-On Soccer (C) | 2 MB | `FAC29677` | 11 read(s) with a wait routine |  |
| Heavy Nova (JU) [!] | 1 MB | `F6B6A9D8` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| High School Soccer - Kunio Kun (J) [!] | 512 KB | `F49C3A86` | standard routine rearranged in place |  |
| High Seas Havoc (U) [!] | 1 MB | `17BE551C` | standard routine rearranged in place |  |
| Hit The Ice (U) [c][!] | 512 KB | `85B23606` | standard routine rearranged in place |  |
| Home Alone (U) [!] | 512 KB | `AA0D4387` | 1 read(s) with a wait routine |  |
| Humans. The (U) [!] | 1 MB | `A0CF4366` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Hurricanes (JUE) [!] | 2 MB | `DECCC874` | 4 read(s) with a wait routine |  |
| Hybrid Front, The (J) [!] | 3 MB | `04F02687` | standard routine rearranged in place |  |
| Hyper Dunk - The Playoff Edition (E) [!] | 2 MB | `F27C576A` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Hyper Marbles (J) [!] | 256 KB | `83BB2799` | standard routine rearranged in place |  |
| Immortal, The (J) | 2 MB | `C99FAD92` | 2 read(s) with a wait routine |  |
| Incredible Hulk, The (JUE) [!] | 2 MB | `84A5A2DC` | standard routine rearranged in place |  |
| Insector X (JU) (Jun 1990) [!] | 512 KB | `9625C434` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Insector X (U) | 512 KB | `2BF02BC3` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Insector X (U) (Jul 1990) [!] | 512 KB | `70626304` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Itchy and Scratchy (UE) | 1 MB | `3100C595` | 4 read(s) with a wait routine |  |
| Itchy and Scratchy Game, The (JEU) | 1 MB | `81B7725D` | 4 read(s) with a wait routine |  |
| Izzy's Quest for the Olympic Rings (F) [!] | 2 MB | `77B416E4` | standard routine rearranged in place |  |
| J. League Pro Striker (J) (REV 00) [c][!] | 1 MB | `EC229156` | 7 read(s) with a wait routine |  |
| J. League Pro Striker (JE) (REV 03) [c][!] | 1 MB | `2D5B7A11` | 7 read(s) with a wait routine |  |
| J. League Pro Striker 2 (J) [!] | 2 MB | `9FE71002` | 7 read(s) with a wait routine |  |
| J. League Pro Striker Final Stage (1) [c][!] | 2 MB | `E35E25FB` | 7 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Jack Nicklaus' Power Challenge Golf (JUE) [!] | 1 MB | `5545E909` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| James Pond 3 - Operation Starfish (UEJ) [!] | 2 MB | `26F64B2A` | 2 read(s) with a wait routine |  |
| Janou Touryumon (J) [!] | 1 MB | `7011E8EB` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Jantei Monogatari (J) | 1 MB | `8A1B19AD` | standard routine rearranged in place |  |
| Jennifer Capriati Tennis (U) [!] | 512 KB | `AB2ABC8E` | standard routine rearranged in place |  |
| Jewel Master (J) [c][!] | 512 KB | `2CF6926C` | standard routine rearranged in place |  |
| Jewel Master (U) [!] | 512 KB | `CEE98813` | standard routine rearranged in place |  |
| John Madden NFL 94 (UEJ) [c][!] | 2 MB | `D14B811B` | 2 read(s) with a wait routine |  |
| Jordan vs Bird - Super One-on-One (J) (REV 00) [!] | 512 KB | `8837E896` | 6 read(s) with a wait routine |  |
| Jordan vs Bird - Super One-on-One (U) (REV 00) [!] | 512 KB | `22D77E6D` | 4 read(s) with a wait routine |  |
| Jordan vs Bird - Super One-on-One (U) (REV 01) [!] | 512 KB | `4D3DDD7C` | 6 read(s) with a wait routine |  |
| JuJu Densetsu (J) | 512 KB | `D09B1EF1` | 2 read(s) with a wait routine |  |
| Junction (JU) [!] | 512 KB | `94CDCE8D` | 2 read(s) with a wait routine |  |
| Jungle Strike (JU) | 2 MB | `BA7A870B` | 2 read(s) with a wait routine |  |
| Jungle Strike (UEJ) [!] | 2 MB | `A5D29735` | 2 read(s) with a wait routine |  |
| Jurassic Park - Rampage Edition (UJE) [!] | 2 MB | `98B4AA1B` | 20 read(s) with a wait routine |  |
| Justice League Task Force (F) [!] | 3 MB | `2A60EBE9` | 8 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Ka-Ge-Ki - Fists of Steel (J) | 1 MB | `391866A1` | standard routine rearranged in place |  |
| Ka-Ge-Ki - Fists of Steel (U) [!] | 1 MB | `EFFC0FA6` | standard routine rearranged in place |  |
| Kawasaki Superbike Challenge (JUE) [!] | 1 MB | `631CC8E9` | 6 read(s) with a wait routine |  |
| Kick Off 3 - European Challenge (E) [!] | 1 MB | `BC37401A` | 2 read(s) with a wait routine |  |
| Kid Chameleon (JUE) [!] | 1 MB | `CE36E6CC` | standard routine rearranged in place |  |
| King Colossus (J) | 1 MB | `FFE7B3C7` | standard routine rearranged in place |  |
| King of Fighters '98, The (Unl) [!] | 2 MB | `C79E1074` | standard routine rearranged in place |  |
| King of the Monsters 2 (U) [!] | 2 MB | `EE1638AC` | 1 read(s) with a wait routine |  |
| Knuckles in Sonic 2 GHZ v0.1 | 3864068 bytes | `999C1F35` | standard routine rearranged in place |  |
| Koutetsu Teikoku (J) [!] | 1 MB | `755D0B8A` | 2 read(s) with a wait routine |  |
| Kujaku-Ou 2 (J) [!] | 384 KB | `AFFD56BC` | standard routine rearranged in place |  |
| Labyrinth of Death (J) [!] | 256 KB | `A6D7E02D` | standard routine rearranged in place |  |
| Land Stalker (U) | 2 MB | `1F1CB2D2` | 2 read(s) with a wait routine |  |
| Landstalker - The Treasures of King Nole (E) (Eng) [!] | 2 MB | `E3C65277` | 2 read(s) with a wait routine |  |
| Landstalker - The Treasures of King Nole (E) (Fre) | 2 MB | `5DE7D917` | 2 read(s) with a wait routine |  |
| Landstalker - The Treasures of King Nole (E) (Ger) [!] | 2 MB | `10FEDB8F` | 2 read(s) with a wait routine |  |
| Landstalker - The Treasures of King Nole (J) [!] | 2 MB | `60D4CEDB` | 2 read(s) with a wait routine |  |
| Landstalker - The Treasures of King Nole (U) [!] | 2 MB | `FBBB5B97` | 2 read(s) with a wait routine |  |
| Langrisser Hikari (J) [!] | 512 KB | `B6EA5016` | standard routine rearranged in place |  |
| Lemmings (E) [!] | 1 MB | `6A1A4579` | 11 read(s) with a wait routine |  |
| Lemmings (JU) (REV 00) [!] | 1 MB | `F015C2AD` | 11 read(s) with a wait routine |  |
| Lemmings (JU) (REV 01) [!] | 1 MB | `68C70362` | 11 read(s) with a wait routine |  |
| Lemmings (U) | 1 MB | `40A27565` | 11 read(s) with a wait routine |  |
| Lethal Enforcers (E) [!] | 2 MB | `CA2BF99D` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Lethal Enforcers (J) | 2 MB | `F25F1E49` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Lethal Enforcers (U) [!] | 2 MB | `51D9A84A` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| LHX Attack Helicopter (J) | 1 MB | `224FF103` | 2 read(s) with a wait routine |  |
| LHX Attack Helicopter (U) [!] | 1 MB | `70C3428D` | 2 read(s) with a wait routine |  |
| Liberty or Death (U) [!] | 2 MB | `2ADB0364` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Light Crusader (4) [!] | 2 MB | `BEB715DC` | 6 read(s) with a wait routine |  |
| Light Crusader (A) | 2 MB | `52C7252B` | 6 read(s) with a wait routine |  |
| Light Crusader (B) [!] | 2 MB | `237076A4` | 6 read(s) with a wait routine |  |
| Light Crusader (K) | 2 MB | `6D0CBCB2` | 6 read(s) with a wait routine |  |
| Link Dragon (Unl) [c] | 256 KB | `1B86E623` | 2 read(s) with a wait routine |  |
| Lord Monarch (J) [!] | 2 MB | `238BF5DB` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Lost Vikings, The (E) | 1 MB | `17BED25F` | 5 read(s) with a wait routine |  |
| Lotus Turbo Challenge (EU) [!] | 1 MB | `A3CF6E9C` | 6 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| M.U.S.H.A (U) [!] | 512 KB | `58A7F7B4` | standard routine rearranged in place |  |
| M1 Abrams Battle Tank (JUE) (REV 01) [!] | 512 KB | `1E2F74CF` | 2 read(s) with a wait routine |  |
| Madden NFL 95 (JUE) [!] | 2 MB | `DB0BE0C2` | 2 read(s) with a wait routine |  |
| Madden NFL 96 (F) [!] | 2 MB | `F126918B` | 2 read(s) with a wait routine |  |
| Madden NFL 97 (F) [!] | 2 MB | `C4B4E112` | 2 read(s) with a wait routine |  |
| Madden NFL 98 (4) [c][!] | 2 MB | `E051EA62` | 2 read(s) with a wait routine |  |
| Madden NFL 98 (U) | 2 MB | `21C4A9A7` | 2 read(s) with a wait routine |  |
| Madou Monogatari I (J) [!] | 2 MB | `DD82C401` | 2 read(s) with a wait routine |  |
| Magical Taluluto Adventure (J) [!] | 512 KB | `F11060A5` | 2 read(s) with a wait routine |  |
| Majikaru Hashito no Butsutobi Turbo! Daibouken (JU) [!] | 512 KB | `E43E853D` | standard routine rearranged in place |  |
| Mamono Hunter Yohko - Makai Kara no Tenkosei (J) [!] | 512 KB | `10BB359B` | 2 read(s) with a wait routine |  |
| Maou Renjishi (J) [c][!] | 512 KB | `24A7F28C` | standard routine rearranged in place |  |
| Mario Andretti Racing (UEJ) [!] | 2 MB | `7F1DC0AA` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Marvel Land (J) [!] | 1 MB | `5D162D21` | standard routine rearranged in place |  |
| Marvel Land (U) [!] | 1 MB | `CD7EEEB7` | standard routine rearranged in place |  |
| Master of Monsters (J) | 512 KB | `D51EE8C2` | standard routine rearranged in place |  |
| Master of Monsters (U) [!] | 512 KB | `91354820` | standard routine rearranged in place |  |
| Master of Weapon (U) | 512 KB | `AF788E8F` | standard routine rearranged in place |  |
| Maten Densetsu (J) | 1 MB | `B804A105` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Math Blaster - Episode 1 (U) [!] | 1 MB | `D055A462` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mazin Saga (J) | 1 MB | `45B3A34B` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mazin Saga (U) [!] | 1 MB | `1BD9FEF1` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mazin Wars (E) | 1 MB | `4B07A105` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| McDonald's Treasure Land Adventure (E) | 1 MB | `6AB6A8DA` | 4 read(s) with a wait routine |  |
| McDonald's Treasure Land Adventure (J) [R-Jap-Eur] | 1 MB | `FEBCFD06` | 4 read(s) with a wait routine |  |
| McDonald's Treasure Land Adventure (U) [!] | 1 MB | `04EF4899` | 4 read(s) with a wait routine |  |
| Mega Bomberman (JUE) [!] | 1 MB | `4BD6667D` | 3 read(s) with a wait routine |  |
| Mega Bomberman (UE) | 1 MB | `E41C8C23` | 3 read(s) with a wait routine |  |
| Mega CDX bios | 128 KB | `4A940D4A` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Mega Games 10 in 1 (F) [!] | 4 MB | `C19AE368` | standard routine rearranged in place; 18 read(s) with a wait routine |  |
| Mega Man - The Wily Wars (E) | 2 MB | `DCF6E8B2` | 2 read(s) with a wait routine |  |
| Mega Net | 256 KB | `FAB33CC2` | 2 read(s) with a wait routine |  |
| Mega Q - The Party Quiz Game (J) | 1 MB | `9D4B447A` | 1 read(s) with a wait routine |  |
| MegaCD Model 1 BIOS V1.00 (E) (Oct 1992) [!] | 128 KB | `529AC15A` | standard routine rearranged in place | A verified patch for this ROM is in the main folder |
| MegaCD Model 1 BIOS V1.00 (J) (Dec 1991) [!] | 128 KB | `550F30BB` | standard routine rearranged in place |  |
| MegaCD Model 1 BIOS V1.01 (J) (Dec 1991) | 128 KB | `9D2DA8F2` | standard routine rearranged in place | A verified patch for this ROM is in the main folder |
| MegaCD Model 2 BIOS V2.00 (E) (Jun 1993) | 128 KB | `D344F125` | standard routine rearranged in place |  |
| MegaCD Model 2 BIOS V2.00 (E) (Mar 1993) [!] | 128 KB | `0507B590` | standard routine rearranged in place |  |
| MegaGames 3in1 Vol 1 (S-HangOn WCupItal90 Columns) (E) [!] | 1 MB | `DB753224` | 5 read(s) with a wait routine |  |
| MegaGames 3in1 Vol 1 (S-HangOn WCupItal90 Columns) (U) | 1 MB | `79B2F941` | 5 read(s) with a wait routine |  |
| MegaGames 3in1 Vol 2 (G-Axe SofRage Rev-Shinobi) (E) [!] | 2 MB | `30D59F2F` | standard routine rearranged in place; 6 read(s) with a wait routine |  |
| MegaGames 3in1 Vol 3 (STBlade SMonacoGP AlienStorm) (E) [!] | 2 MB | `B4247D98` | standard routine rearranged in place; 4 read(s) with a wait routine |  |
| MegaGames 4in1 - Classic Collection (F) [!] | 2 MB | `73F948B1` | standard routine rearranged in place; 15 read(s) with a wait routine |  |
| MegaGames 4in1 - Classic Collection (U) | 2 MB | `C370F3C5` | standard routine rearranged in place; 15 read(s) with a wait routine |  |
| MegaGames 6in1 US (GoldenAxe SuperHangOn) (4) [!] | 3 MB | `1A6F45DC` | standard routine rearranged in place; 16 read(s) with a wait routine |  |
| MegaGames 6in1 Vol 1 (S-HangOn WCup-Italia) (F) [!] | 3 MB | `B66FB80D` | 16 read(s) with a wait routine |  |
| MegaGames 6in1 Vol 3 (Soccer S-MonacoGP) (F) [!] | 3 MB | `FE3E7E4F` | standard routine rearranged in place; 14 read(s) with a wait routine |  |
| MegaGames 6in1 Vol 3 (Soccer S-MonacoGP) (U) | 3 MB | `BAF58DCA` | standard routine rearranged in place; 14 read(s) with a wait routine |  |
| Megaman The Wily's War (UE) | 2 MB | `E24D9381` | 2 read(s) with a wait routine |  |
| Meganet BIOS (JUE) | 512 KB | `98DEE72B` | 4 read(s) with a wait routine |  |
| Mercs (JUE) [!] | 1 MB | `16113A72` | standard routine rearranged in place |  |
| Michael Jackson's Moonwalker (JUE) (REV 00) [!] | 512 KB | `6A70791B` | standard routine rearranged in place |  |
| Michael Jackson's Moonwalker (JUE) (REV 01) [!] | 512 KB | `11CE1F9E` | standard routine rearranged in place |  |
| Mickey Mania - Timeless Adventures of Mickey Mouse (E) [!] | 2 MB | `CB5A8B85` | 2 read(s) with a wait routine |  |
| Mickey Mania - Timeless Adventures of Mickey Mouse (U) [!] | 2 MB | `629E5963` | 2 read(s) with a wait routine |  |
| Mickey Mouse - Fantasia (U) (REV 00) [!] | 512 KB | `34E04627` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Mickey Mouse - Fantasia (U) (REV 01) [!] | 512 KB | `FC43DF2D` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Mickey Mouse - World of Illusion (E) [!] | 1 MB | `121C6A49` | standard routine rearranged in place |  |
| Mickey Mouse - World of Illusion (J) | 1 MB | `CB9EE238` | standard routine rearranged in place |  |
| Mickey Mouse - World of Illusion (U) [!] | 1 MB | `921EBD1C` | standard routine rearranged in place |  |
| Mickey's Ultimate Challenge (U) [!] | 1 MB | `30B512EE` | 2 read(s) with a wait routine |  |
| Midnight Resistance (J) | 1 MB | `8F3F6E4D` | standard routine rearranged in place |  |
| Midnight Resistance (U) [!] | 1 MB | `187C6AF6` | standard routine rearranged in place |  |
| Mig-29 Fulcrum (E) | 1 MB | `70B0A5D7` | 7 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mig-29 Fulcrum (U) [!] | 1 MB | `59CCABB2` | 7 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mighty Morphin Power Rangers - The Movie (4) [!] | 2 MB | `AA941CBC` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mike Ditka Power Football (U) [!] | 1 MB | `6078B310` | 2 read(s) with a wait routine |  |
| Minato no Toreijia (J) | 1 MB | `BD89FD09` | standard routine rearranged in place |  |
| Minnesota Fats Pool Legend (4) [!] | 1 MB | `38174F40` | 4 read(s) with a wait routine |  |
| MLBPA Baseball (UEJ) [!] | 2 MB | `14A8064D` | 4 read(s) with a wait routine |  |
| Moonwalker (UE) | 512 KB | `D7A596EC` | standard routine rearranged in place |  |
| Mortal Combat 5 (Unl) [c][!] | 2 MB | `11E367A1` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Mortal Kombat (JUE) (REV 00) [!] | 2 MB | `1AA3A207` | 7 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Mr. Nutz (E) [!] | 1 MB | `0786EA0B` | 2 read(s) with a wait routine |  |
| Ms. Pac-Man (U) [!] | 128 KB | `AF041BE6` | 2 read(s) with a wait routine |  |
| Multitap - IO Sample Program of Nov 28 1992 (JUE) [c][!] | 256 KB | `17BA99E4` | 1 read(s) with a wait routine |  |
| Mystic Defender (JUE) (REV 00) | 512 KB | `F9CE1AB8` | standard routine rearranged in place |  |
| Mystic Defender (JUE) (REV 01) [!] | 512 KB | `50FD5D93` | standard routine rearranged in place |  |
| Mystic Defender (UE) | 512 KB | `441BF54F` | standard routine rearranged in place |  |
| Mystical Fighter (U) [c][!] | 512 KB | `B2F2A69B` | standard routine rearranged in place |  |
| NBA Action (U) [!] | 2 MB | `99C348BA` | 5 read(s) with a wait routine |  |
| NBA Action 95 (UEJ) [!] | 2 MB | `AA7006D6` | 2 read(s) with a wait routine |  |
| NBA Hang Time (4) [!] | 3 MB | `176B0338` | 3 read(s) with a wait routine |  |
| NBA Hang Time (8) [!] | 3 MB | `EDB4D4AA` | 3 read(s) with a wait routine |  |
| NBA Jam (EU) (REV 00) [!] | 2 MB | `10FA248F` | 6 read(s) with a wait routine |  |
| NBA Jam (EU) (REV 01) [!] | 2 MB | `EB8360E6` | 6 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| NBA Jam Tournament Edition (JUE) (REV 00) [!] | 3 MB | `E9FFCB37` | 6 read(s) with a wait routine |  |
| NBA Jam Tournament Edition (JUE) (REV 01) [!] | 3 MB | `6E25EBF0` | 6 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| NBA Live 95 (UEJ) [!] | 2 MB | `66018ABC` | 7 read(s) with a wait routine |  |
| NBA Live 96 (F) [!] | 2 MB | `49DE0062` | 7 read(s) with a wait routine |  |
| NBA Live 97 (F) [!] | 2 MB | `7024843A` | 7 read(s) with a wait routine |  |
| NBA Pro Basketball '94 (J) | 2 MB | `EEA19BCE` | 3 read(s) with a wait routine |  |
| NBA Pro Basketball - Bulls vs Lakers (J) [!] | 1 MB | `4416CE39` | 2 read(s) with a wait routine |  |
| NBA Showdown 94 (UE) [!] | 2 MB | `160B7090` | 2 read(s) with a wait routine |  |
| New Zealand Story, The (J) [!] | 512 KB | `1C77AD21` | standard routine rearranged in place |  |
| NHL 95 (EUJ) [!] | 2 MB | `E8EE917E` | 2 read(s) with a wait routine |  |
| NHL 95 Elitserien (E) [c][!] | 2 MB | `E10A25C0` | 2 read(s) with a wait routine |  |
| NHL 96 (F) [!] | 2 MB | `8135702C` | 2 read(s) with a wait routine |  |
| NHL 96 Elitserien (8) | 2 MB | `9821D0A3` | 2 read(s) with a wait routine |  |
| NHL 97 (F) [!] | 2 MB | `F067C103` | 2 read(s) with a wait routine |  |
| NHL 98 (4) [c][!] | 2 MB | `7B64CD98` | 2 read(s) with a wait routine |  |
| NHL Hockey 94 (UE) [!] | 1 MB | `9438F5DD` | 2 read(s) with a wait routine |  |
| Nikkan Sports Pro Yakyuu Van (J) [!] | 512 KB | `C3655A59` | standard routine rearranged in place |  |
| Nobunaga no Yabou - Zenkokuban (J) | 512 KB | `1381B313` | 5 read(s) with a wait routine |  |
| Nobunaga no Yabou Haouden - Lord of Darkness (J) [!] | 2 MB | `96C01FC6` | 5 read(s) with a wait routine |  |
| Nobunaga's Ambition (U) [!] | 512 KB | `B9BC07BC` | 5 read(s) with a wait routine |  |
| Nobunaga's no Yabou (J) [!] | 1 MB | `30BF8637` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Ooze, The (5) | 1 MB | `1C0DD42F` | standard routine rearranged in place; 3 read(s) with a wait routine |  |
| Ooze, The (A) | 1 MB | `E16B102C` | standard routine rearranged in place; 3 read(s) with a wait routine |  |
| Operation Europe - Path to Victory 1939-1945 (U) [!] | 1 MB | `E7CBA1D8` | standard routine rearranged in place |  |
| OutRun (JU) [!] | 1 MB | `FDD9A8D2` | standard routine rearranged in place |  |
| OutRun 2019 (E) [!] | 1 MB | `5CB3536A` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| OutRun 2019 (J) | 1 MB | `0EAC7440` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| OutRun 2019 (U) [!] | 1 MB | `E32E17E2` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| OutRunners (J) | 2 MB | `E164A09F` | 2 read(s) with a wait routine |  |
| OutRunners (U) [!] | 2 MB | `EDE636B9` | 2 read(s) with a wait routine |  |
| Pac-Man 2 - The New Adventures (U) [!] | 2 MB | `FE7A7ED1` | 6 read(s) with a wait routine |  |
| Pachinko Canyon (J) [!] | 1 MB | `9D137E7F` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Pacific Theater of Operations (J) [c][!] | 1 MB | `9B08E4E4` | standard routine rearranged in place |  |
| Pacific Theater of Operations (U) [!] | 1 MB | `D9D4C6E2` | standard routine rearranged in place |  |
| Paddle Fighter (J) [!] | 256 KB | `3D8147E6` | standard routine rearranged in place |  |
| Pagemaster, The (E) | 2 MB | `79A180E2` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Pagemaster, The (U) [!] | 2 MB | `75A96D4E` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Pat Riley Basketball (U) [!] | 512 KB | `3D9318A7` | standard routine rearranged in place |  |
| Pebble Beach Golf Links (E) | 2 MB | `6CFC7297` | 2 read(s) with a wait routine |  |
| Pebble Beach Golf Links (J) | 1536 KB | `96ED2E5D` | 2 read(s) with a wait routine |  |
| Pebble Beach Golf Links (U) [!] | 2 MB | `95823C43` | 2 read(s) with a wait routine |  |
| pebble_beach_golf | 2 MB | `9D5EC55A` | 2 read(s) with a wait routine |  |
| Pele's World Tournament Soccer (JUE) [!] | 2 MB | `05A486E9` | 10 read(s) with a wait routine |  |
| Pengo (F) [!] | 1 MB | `D1E2324B` | 5 read(s) with a wait routine |  |
| PGA European Tour (UEJ) [!] | 1 MB | `8CA45ACD` | 1 read(s) with a wait routine |  |
| PGA Tour 96 (F) [!] | 2 MB | `9698BBDE` | 2 read(s) with a wait routine |  |
| PGA Tour Golf (U) (REV 01) [!] | 512 KB | `0489FF8E` | 1 read(s) with a wait routine |  |
| PGA Tour Golf (U) (REV 02) [!] | 512 KB | `C1F0B4E1` | 1 read(s) with a wait routine |  |
| PGA Tour Golf 2 (J) | 1 MB | `C05B7A4A` | 1 read(s) with a wait routine |  |
| PGA Tour Golf 2 (UEJ) (REV 00) [c][!] | 1 MB | `16B2D816` | 1 read(s) with a wait routine |  |
| PGA Tour Golf 2 (UEJ) (REV 01) [!] | 1 MB | `E82B8606` | 1 read(s) with a wait routine |  |
| PGA Tour Golf 3 (UEJ) [!] | 2 MB | `AEB3F65F` | 1 read(s) with a wait routine |  |
| Phantasy Star - The End of the Millenium (J) [!] | 3 MB | `F0BFAD42` | standard routine rearranged in place |  |
| Phantasy Star II (UE) (REV 01) | 768 KB | `0D07D0EF` | standard routine rearranged in place |  |
| Phantasy Star II (UE) (REV 02) [!] | 768 KB | `904FA047` | standard routine rearranged in place |  |
| Phantasy Star II - Anne's Adventure (J) | 256 KB | `FAFA5B6F` | standard routine rearranged in place |  |
| Phantasy Star II - Huey's Adventure (J) | 256 KB | `1A076F83` | standard routine rearranged in place |  |
| Phantasy Star II - Kind's Adventure (J) | 256 KB | `349A4B78` | standard routine rearranged in place |  |
| Phantasy Star II - Kind's Adventure (J) [!] | 256 KB | `C334F308` | standard routine rearranged in place |  |
| Phantasy Star II - Shilka's Adventure (J) | 256 KB | `1F83BEB2` | standard routine rearranged in place |  |
| Phantasy Star III - Generations of Doom (J) | 768 KB | `6C48C06F` | 2 read(s) with a wait routine |  |
| Phantasy Star III - Generations of Doom (UE) [!] | 768 KB | `C6B42B0F` | 2 read(s) with a wait routine |  |
| Phantasy Star IV (4) [!] | 3 MB | `FE236442` | standard routine rearranged in place |  |
| phantasy_star4 | 3 MB | `3517EF45` | standard routine rearranged in place |  |
| Phantom 2040 (4) [!] | 2 MB | `FB36E1F3` | 9 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Phantom 2040 (8) | 2 MB | `B024882E` | 9 read(s) with a wait routine | A verified patch for this ROM is in the main folder |
| Pinocchio (4) [!] | 3 MB | `CD4128D8` | 4 read(s) with a wait routine |  |
| Pinocchio (8) | 3 MB | `28014BDC` | 4 read(s) with a wait routine |  |
| Pioneer LaserActive Bios v1.02 (J) | 128 KB | `00EEDB3A` | standard routine rearranged in place |  |
| Pioneer LaserActive Bios v1.02 (U) | 128 KB | `3B10CF41` | standard routine rearranged in place |  |
| Pirates Gold (U) [!] | 1 MB | `ED50E75C` | 1 read(s) with a wait routine |  |
| Pocahontas (4) [!] | 4 MB | `6DDD1C6D` | 2 read(s) with a wait routine |  |
| Populous 2 - Two Tribes (E) [!] | 1 MB | `EE988BD9` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Populous 2 - Wrath of the Gods (U) | 1 MB | `12FB60FA` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Power Drive (EJU) [!] | 1 MB | `8C00AD61` | 4 read(s) with a wait routine |  |
| Power Instinct (J) [!] | 3 MB | `ABE9C415` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Power Monger (J) | 1 MB | `553289B3` | 2 read(s) with a wait routine |  |
| Power Monger (UEJ) [R-USA][!] | 1 MB | `FB599B86` | 2 read(s) with a wait routine |  |
| Pro Action Replay (JUE) [c][!] | 128 KB | `17255224` | 1 read(s) with a wait routine |  |
| Project Shadow 2 Demo 4 (v1.00) | 1529288 bytes | `A85509B8` | standard routine rearranged in place |  |
| ps4cn_alpha | 4 MB | `6C6BA10F` | standard routine rearranged in place |  |
| Pulseman (J) [c][!] | 2 MB | `138A104E` | 2 read(s) with a wait routine |  |
| Putter Golf (J) [!] | 256 KB | `20F168A6` | standard routine rearranged in place |  |
| Puyo Puyo (J) [!] | 512 KB | `7F26614E` | 4 read(s) with a wait routine |  |
| Puyo Puyo 2 (J) (REV 00) | 2 MB | `51AD7797` | 4 read(s) with a wait routine |  |
| Puyo Puyo 2 (J) (REV 01) [!] | 2 MB | `25B7B2AA` | 4 read(s) with a wait routine |  |
| Puzzle and Action - Ichidant (1) [!] | 2 MB | `7BDEC762` | 1 read(s) with a wait routine |  |
| Puzzle and Action - Tanto (J) [!] | 2 MB | `D2D2D437` | 1 read(s) with a wait routine |  |
| Pyramid Magic (J) [!] | 256 KB | `306D839E` | standard routine rearranged in place |  |
| Pyramid Magic II (J) [!] | 256 KB | `C9DDAC72` | standard routine rearranged in place |  |
| Pyramid Magic III (J) [!] | 256 KB | `8329820A` | standard routine rearranged in place |  |
| Pyramid Magic Special (J) | 256 KB | `153A3AFA` | standard routine rearranged in place |  |
| Race Drivin' (UJE) [!] | 512 KB | `D737CF3D` | 1 read(s) with a wait routine |  |
| Radical Rex (E) | 1 MB | `D02D3282` | 10 read(s) with a wait routine |  |
| Radical Rex (U) [!] | 1 MB | `2E6EEC7E` | 10 read(s) with a wait routine |  |
| Ragnacenty (J) [!] | 2 MB | `6A3F5AE2` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Raiden Trad (JU) [!] | 1 MB | `F839A811` | 2 read(s) with a wait routine |  |
| Rainbow Islands - The Story of Bubble Bobble 2 (JU) [c][!] | 512 KB | `C74DCB35` | standard routine rearranged in place |  |
| Ranger-X (E) [!] | 1 MB | `B8C04804` | standard routine rearranged in place; 8 read(s) with a wait routine |  |
| Ranger-X (U) [!] | 1 MB | `55915915` | standard routine rearranged in place; 8 read(s) with a wait routine |  |
| Rastan Saga 2 (J) [!] | 512 KB | `EBACFB5A` | standard routine rearranged in place |  |
| Rastan Saga 2 (U) [!] | 512 KB | `C7EE8965` | standard routine rearranged in place |  |
| Revenge of Shinobi, The (JUE) (REV 00) [R-USA-Jap][!] | 512 KB | `5C7E5EA6` | 2 read(s) with a wait routine |  |
| Revenge of Shinobi, The (JUE) (REV 01) [R-USA][!] | 512 KB | `05F27994` | 2 read(s) with a wait routine |  |
| Revenge of Shinobi, The (JUE) (REV 02) [R-Eur][!] | 512 KB | `FE91AB7E` | 2 read(s) with a wait routine |  |
| Revenge of Shinobi, The (JUE) (REV 03) | 512 KB | `4D35EBE4` | 2 read(s) with a wait routine |  |
| Richard Scarry's Busytown (UJ) [!] | 2 MB | `7BB60C3F` | 2 read(s) with a wait routine |  |
| Risk (U) [!] | 512 KB | `80416D0D` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Risky Woods (UE) [!] | 1 MB | `D975E93C` | 2 read(s) with a wait routine |  |
| Ristar (J) [!] | 2 MB | `CE464F0E` | standard routine rearranged in place |  |
| Ristar (UE) [!] | 2 MB | `6511AA61` | standard routine rearranged in place |  |
| Robocop vs The Terminator (E) (REV 670) | 2 MB | `85A93F8D` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Robocop vs The Terminator (U) (REV 670) [!] | 2 MB | `BBAD77A4` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Rocket Knight Adventures (E) | 1 MB | `8EEDFD51` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Rocket Knight Adventures (J) | 1 MB | `D1C8C1C5` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Rocket Knight Adventures (U) [!] | 1 MB | `A6EFEC47` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Rocket_Knight_Adventures_[_T_-_Terminus_RC1_(F)]_-_genesis(E) | 1 MB | `8E52F046` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Rockman Megaworld (J) [!] | 2 MB | `85C956EF` | 2 read(s) with a wait routine |  |
| Rockman X3 (Unl) [c][!] | 2 MB | `3EE639F0` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Rocky and Bullwinkle, The Adventures of (U) [!] | 1 MB | `EF02D57B` | standard routine rearranged in place |  |
| Romance of the Three Kingdoms II (J) | 1 MB | `437BA326` | standard routine rearranged in place |  |
| Romance of the Three Kingdoms II (U) [!] | 1 MB | `3D842478` | standard routine rearranged in place |  |
| Romance of the Three Kingdoms III (J) [!] | 1536 KB | `A8DE6AEA` | standard routine rearranged in place |  |
| Romance of the Three Kingdoms III (U) [!] | 1280 KB | `7E41C8FE` | standard routine rearranged in place |  |
| Romance of the Three Kingdoms Part 5 (Chinese) | 2 MB | `CD7E53D0` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Royal Blood (J) | 1 MB | `0E0107F1` | standard routine rearranged in place |  |
| Rugby World Cup 95 (UJE) [!] | 2 MB | `61F90A8A` | 7 read(s) with a wait routine |  |
| Runark (JUE) | 512 KB | `0894D8FB` | standard routine rearranged in place |  |
| S2 Long v1.8 | 1419 KB | `F1D07A8A` | standard routine rearranged in place |  |
| S2&K Long v1.8 | 3328 KB | `4B024D26` | standard routine rearranged in place |  |
| s2longv17b1 | 1474048 bytes | `38023429` | standard routine rearranged in place |  |
| s2rev02 | 1 MB | `F23AD4B3` | standard routine rearranged in place |  |
| S2SMTP | 1521078 bytes | `314A5506` | standard routine rearranged in place |  |
| s2u055b | 1344 KB | `F0614095` | standard routine rearranged in place |  |
| sailor_moon | 2 MB | `3DD848B5` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Saint Sword (J) [c][!] | 512 KB | `3960A00F` | standard routine rearranged in place |  |
| Saint Sword (U) [c][!] | 512 KB | `44F66BFF` | standard routine rearranged in place |  |
| Sangokushi Retsuden (Chinese) | 1 MB | `3B5CC398` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Sangokushi Retsuden (J) [!] | 1 MB | `0F56785A` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Sega Arcade Classics (F) [!] | 512 KB | `8AED2090` | 2 read(s) with a wait routine |  |
| Sega HMD and Tracker Demo - OA7-TST (JUE) [c][!] | 512 KB | `5AFDC704` | 2 read(s) with a wait routine |  |
| SEGA MULTI-GAME MENU V1.00 | 128 KB | `EFD5EEF3` | 2 read(s) with a wait routine |  |
| Sega Sports 1 (Wimbledon, Ult.Soccer, Super Monaco) (E) [!] | 2560 KB | `07FEDAF1` | 8 read(s) with a wait routine |  |
| Sega Subor System Cartridge | 2 MB | `513B2B72` | 1 read(s) with a wait routine |  |
| Sega Top 5 (F) [!] | 2 MB | `61069069` | standard routine rearranged in place; 7 read(s) with a wait routine |  |
| SegaCD Model 1 BIOS V1.10 (U) (Oct 1992) | 128 KB | `C6D10268` | standard routine rearranged in place | A verified patch for this ROM is in the main folder |
| SegaCD Model 2 BIOS V2.00 (U) (Mar 1993) [!] | 128 KB | `340B4BE4` | standard routine rearranged in place |  |
| SegaCD Model 2 BIOS V2.00W (U) (Jun 1993) | 128 KB | `9F6F6276` | standard routine rearranged in place |  |
| SegaCD Model 2 BIOS V2.11 (U) (Jun 1993) [!] | 128 KB | `B0519ED3` | standard routine rearranged in place |  |
| Sensible Soccer - International Edition (E) [!] | 512 KB | `04E3BCCA` | 4 read(s) with a wait routine |  |
| Shadow Blasters (U) [c][!] | 512 KB | `713D377B` | standard routine rearranged in place |  |
| Shane Warne Cricket (E) [c][!] | 1 MB | `68865F6F` | standard routine rearranged in place |  |
| Shanghai 2 - Dragon's Eye (U) [!] | 1 MB | `EBE9E840` | 5 read(s) with a wait routine |  |
| shanghai3 | 256 KB | `5C6674CF` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Shin Changsegi - Ragnacenty (K) | 2 MB | `77B5B10B` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Shining and the Darkness (J) | 1 MB | `496AF51C` | standard routine rearranged in place |  |
| Shining Force (J) [!] | 1536 KB | `9378FBCD` | standard routine rearranged in place |  |
| Shining Force (U) [!] | 1536 KB | `E0594ABE` | standard routine rearranged in place |  |
| Shining Force II (E) [!] | 2 MB | `83CB46D1` | 8 read(s) with a wait routine |  |
| Shining Force II (U) [!] | 2 MB | `4815E075` | 8 read(s) with a wait routine |  |
| Shining Force II - Return of the King (J) [!] | 2 MB | `0288F3E1` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Shining in the Darkness (U) [!] | 1 MB | `4D2785BC` | standard routine rearranged in place |  |
| shining_in_darkness | 1 MB | `C7A40A49` | standard routine rearranged in place |  |
| Shinobi 3 - Return of the Ninja Master (E) [c][!] | 1 MB | `0B6D3EB5` | 8 read(s) with a wait routine |  |
| Shinobi 3 - Return of the Ninja Master (U) [!] | 1 MB | `5381506F` | 8 read(s) with a wait routine |  |
| shinobi2 | 512 KB | `E1ABB151` | 2 read(s) with a wait routine |  |
| Shiten Myooh (J) [c][!] | 512 KB | `7E729693` | standard routine rearranged in place |  |
| Shougino (J) | 256 KB | `4148F816` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Shove It - The Warehouse Game (U) [!] | 128 KB | `C51F40CB` | 2 read(s) with a wait routine |  |
| Side Pocket (E) | 1 MB | `36E08145` | standard routine rearranged in place |  |
| Side Pocket (JU) [!] | 1 MB | `AF9F275D` | standard routine rearranged in place |  |
| side_pocket | 1 MB | `1F289095` | standard routine rearranged in place |  |
| Skitchin (UEJ) [!] | 2 MB | `F785F9D7` | 6 read(s) with a wait routine |  |
| Slam Dunk - Shikyou Gekitotsu! (1) | 2 MB | `CDF5678F` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| slap_fite | 1 MB | `BFCEA8FF` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Slaughter Sport (UE) [c][!] | 1 MB | `AAB2C6C4` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Smart Mouse (Unl) [c] | 512 KB | `DECDF740` | standard routine rearranged in place |  |
| smurfs | 1 MB | `74D0E5DC` | standard routine rearranged in place |  |
| Smurfs 2, The (E) [!] | 1 MB | `B28BDD69` | 6 read(s) with a wait routine |  |
| Smurfs, The (E) [!] | 1 MB | `88B30EFF` | standard routine rearranged in place |  |
| smurfs2 | 1 MB | `D8C6747C` | 6 read(s) with a wait routine |  |
| Snake Rattle 'n' Roll (E) [c][!] | 512 KB | `543BED30` | standard routine rearranged in place |  |
| Snow Brothers (JUE) [c][!] | 1 MB | `11B56228` | 4 read(s) with a wait routine |  |
| snow_bros | 1 MB | `A102D5E0` | 4 read(s) with a wait routine |  |
| Socket (JUE) [!] | 1 MB | `3C14E15A` | standard routine rearranged in place |  |
| Sokoban (J) | 256 KB | `40F4AACC` | 2 read(s) with a wait routine |  |
| Sol-Deace (U) [!] | 1 MB | `A77E4E9F` | standard routine rearranged in place |  |
| Soleil (E) (Eng) | 2 MB | `A30EBDB1` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Soleil (E) (Fre) | 2 MB | `08DC1EAD` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Soleil (E) (Ger) [!] | 2 MB | `332B9ECD` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Soleil (E) (Spa) | 2 MB | `9ED4C323` | standard routine rearranged in place; 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Sonic & Knuckles | 2 MB | `16EC7FC8` | standard routine rearranged in place |  |
| Sonic 1 Gaslight | 526491 bytes | `B371CFDF` | standard routine rearranged in place |  |
| Sonic 1 Spindash | 524614 bytes | `98EA1053` | standard routine rearranged in place |  |
| Sonic 1 Title Cards | 526491 bytes | `90934613` | standard routine rearranged in place |  |
| Sonic 2 AlE Rel3·1 | 1325584 bytes | `5D9CF080` | standard routine rearranged in place |  |
| Sonic 2 Beta Lost Tiles | 1 MB | `F5D026F8` | standard routine rearranged in place |  |
| Sonic 2 Beta Title Cards | 1052592 bytes | `672B60E6` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.01 | 1052592 bytes | `6E60BE35` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.02 | 1067136 bytes | `29EECE09` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.02a | 1067136 bytes | `F3395995` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.03 | 1071152 bytes | `BD81C76F` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.04 | 1094444 bytes | `4284576C` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.05 | 1081904 bytes | `DD5A73F3` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.06 | 1 MB | `5A94302E` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.06a | 1 MB | `20A8DC8A` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.07 | 1 MB | `42529355` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.08 | 1 MB | `1DE3B96A` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.09 | 1 MB | `287CA01F` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.10 | 1 MB | `F3FF4D3B` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.11 | 1 MB | `28F866FA` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.12 | 1 MB | `33395366` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.13 | 1 MB | `78CFF078` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.14 | 1 MB | `D7C557DA` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.15 | 1 MB | `C9977762` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.16 | 1 MB | `DFBF3DB0` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.16a | 1 MB | `C4E169B1` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.17 | 1 MB | `0F09B8DB` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.18 | 1 MB | `9640BFEE` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.19 | 1 MB | `10931427` | standard routine rearranged in place |  |
| Sonic 2 Delta 0.20 | 1 MB | `1CF80658` | standard routine rearranged in place |  |
| Sonic 2 Delta II v0.5 | 1109648 bytes | `F95DE5FA` | standard routine rearranged in place |  |
| Sonic 2 Delta II v0.5a | 1109648 bytes | `8781EF91` | standard routine rearranged in place |  |
| Sonic 2 Delta II v0.8 | 1508712 bytes | `07E2CA40` | standard routine rearranged in place |  |
| Sonic 2 Delta II v0.9 | 1508712 bytes | `F8E1F1B2` | standard routine rearranged in place |  |
| Sonic 2 Delta II v1.0 | 1508560 bytes | `417958D4` | standard routine rearranged in place |  |
| Sonic 2 Delta II v1.0a | 1508560 bytes | `85486E22` | standard routine rearranged in place |  |
| Sonic 2 Delta III v0.1 | 1383664 bytes | `B821A51D` | standard routine rearranged in place |  |
| Sonic 2 Delta III v0.2 | 1443232 bytes | `5ED203F7` | standard routine rearranged in place |  |
| Sonic 2 GHZ v0.2 | 1497586 bytes | `DECB907F` | standard routine rearranged in place |  |
| Sonic 2 haz | 1542836 bytes | `9B333809` | standard routine rearranged in place |  |
| Sonic 2 hell | 1320038 bytes | `8A6B7457` | standard routine rearranged in place |  |
| Sonic 2 mecha world | 1509546 bytes | `FC19C7BD` | standard routine rearranged in place |  |
| Sonic 2 Menu no Sonic 1 | 536128 bytes | `7A87D83E` | standard routine rearranged in place |  |
| sonic 2 rabid | 1081398 bytes | `1A01E239` | standard routine rearranged in place |  |
| Sonic 2 remix | 1545396 bytes | `93776911` | standard routine rearranged in place |  |
| sonic 2 salus | 1514928 bytes | `2E9F384B` | standard routine rearranged in place |  |
| Sonic 2 ultimate | 1554016 bytes | `167CBF2D` | standard routine rearranged in place |  |
| Sonic 2 xp | 1109615 bytes | `39B21DAD` | standard routine rearranged in place |  |
| Sonic 2K (1 Mb) | 1 MB | `8E3E172D` | standard routine rearranged in place |  |
| Sonic 2K (1 Mb) rev 1 | 1 MB | `7BD21906` | standard routine rearranged in place |  |
| Sonic 2K Upmem | 1448784 bytes | `E7382503` | standard routine rearranged in place |  |
| Sonic 3 Delta v0.1 | 2444832 bytes | `C2D15FBF` | standard routine rearranged in place |  |
| Sonic 3 Delta v0.1a | 2444832 bytes | `412FFCA4` | standard routine rearranged in place |  |
| Sonic amy | 512 KB | `CEF4F815` | standard routine rearranged in place |  |
| Sonic and Knuckles & Sonic 1 (JUE) [!] | 2560 KB | `E01F6ED5` | standard routine rearranged in place |  |
| Sonic and Knuckles & Sonic 2 (JUE) [!] | 3328 KB | `2AC1E7C6` | standard routine rearranged in place |  |
| Sonic and Knuckles & Sonic 3 (JUE) [!] | 4 MB | `63522553` | standard routine rearranged in place |  |
| Sonic and Knuckles (JUE) [!] | 2 MB | `0658F691` | standard routine rearranged in place |  |
| Sonic chao walker | 512 KB | `A27C88EB` | standard routine rearranged in place |  |
| Sonic Compilation (A) (REV 00) [!] | 3 MB | `8C70B84E` | standard routine rearranged in place; 9 read(s) with a wait routine |  |
| Sonic Compilation (F) (REV 01) [!] | 3 MB | `95B5E8D7` | standard routine rearranged in place; 9 read(s) with a wait routine |  |
| Sonic dr iks | 512 KB | `EF5C39A7` | standard routine rearranged in place |  |
| Sonic Eraser (J)(T+Eng-Derrick Sobodash) | 256 KB | `26D9BC32` | standard routine rearranged in place |  |
| Sonic Jam 6 (Unl) | 2 MB | `87D86501` | 2 read(s) with a wait routine |  |
| Sonic Knucle | 2 MB | `25B90399` | standard routine rearranged in place |  |
| Sonic Psycho | 512 KB | `7D00E4B2` | standard routine rearranged in place |  |
| Sonic richrodgers | 512 KB | `E38ABD5D` | standard routine rearranged in place |  |
| Sonic Special Stages (U) [c] | 2560 KB | `19A2C2EF` | standard routine rearranged in place |  |
| Sonic Spinball (E) [!] | 1 MB | `AEA0786D` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Sonic Spinball (J) [!] | 1 MB | `ACD08CE8` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Sonic Spinball (U) (alt music) [!] | 1 MB | `E9960371` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Sonic Spinball (U) [!] | 1 MB | `677206CB` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Sonic the Hedgehog  knux-in-sonic1 | 512 KB | `76537220` | standard routine rearranged in place |  |
| Sonic the Hedgehog (JUE) [R-Jap][!] | 512 KB | `AFE05EEE` | standard routine rearranged in place |  |
| Sonic the Hedgehog (UE) (MegaPlay Arcade Version) | 512 KB | `1B9C2254` | standard routine rearranged in place |  |
| Sonic The Hedgehog - Knuckles In Sonic 1 (V0.02 by Hibernate) | 698536 bytes | `5EEE19D4` | standard routine rearranged in place |  |
| Sonic the Hedgehog - mighty the armadillo v4.16 | 599136 bytes | `93E36639` | standard routine rearranged in place |  |
| Sonic The Hedgehog - Splats The Rabbit (by Hivebrain) | 512 KB | `6A46D0F2` | standard routine rearranged in place |  |
| Sonic the Hedgehog 2 (JUE) [!] | 1 MB | `7B905383` | standard routine rearranged in place | A verified patch for this ROM is in the main folder |
| Sonic the Hedgehog 2 - kojichao - mtam | 1049856 bytes | `8E35F3AB` | standard routine rearranged in place |  |
| Sonic the Hedgehog 2 - projectshadow2 - demo3 | 1553132 bytes | `709FDA35` | standard routine rearranged in place |  |
| Sonic the Hedgehog 3 | 2 MB | `87EEB165` | standard routine rearranged in place |  |
| Sonic the Hedgehog 3 (E) | 2 MB | `6A632503` | standard routine rearranged in place | A verified patch for this ROM is in the main folder; For the de-interleaved (non-SMD) ROM |
| Sonic the Hedgehog 3 (J) [!] | 2 MB | `F4951D1F` | standard routine rearranged in place |  |
| Sonic the Hedgehog 3 (U) [!] | 2 MB | `9BC192CE` | standard routine rearranged in place | A verified patch for this ROM is in the main folder |
| Sonic the Hedgehog hez kte1 | 566368 bytes | `48D2A77A` | standard routine rearranged in place |  |
| Sonic the Hedgehog supersonic in south island adventure v02 | 604367 bytes | `EB0E8A57` | standard routine rearranged in place |  |
| Sonic tikal | 512 KB | `550BC00D` | standard routine rearranged in place |  |
| Sonic ultima 1337 | 512 KB | `6CCDEC22` | standard routine rearranged in place |  |
| Sonic weird | 512 KB | `D52CB68D` | standard routine rearranged in place |  |
| Sonic xmas | 512 KB | `20A24EAD` | standard routine rearranged in place |  |
| sonic1 | 512 KB | `44ECA160` | standard routine rearranged in place |  |
| sonic2 | 1 MB | `AE2D99C5` | standard routine rearranged in place |  |
| sonic2_and_knuckles | 3328 KB | `D708961E` | standard routine rearranged in place |  |
| SONIC3 | 2 MB | `02B4C223` | standard routine rearranged in place |  |
| sonic3_and_knuckles | 4 MB | `5D8F4F5C` | standard routine rearranged in place |  |
| sonic_and_knuckles | 2 MB | `690C7940` | standard routine rearranged in place |  |
| sonic_crackers | 1 MB | `CF1A1F45` | 4 read(s) with a wait routine |  |
| sonic_special_stages | 2560 KB | `85C2F439` | standard routine rearranged in place |  |
| SONICSPN | 1 MB | `E056D49D` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Sorcer Kingdom (J) [c][!] | 1 MB | `944135CA` | standard routine rearranged in place |  |
| Sorcerer's Kingdom (U) (1992) | 1 MB | `CBE6C1EA` | standard routine rearranged in place |  |
| Sorcerer's Kingdom (U) (1993) [!] | 1 MB | `BB1FC9CE` | standard routine rearranged in place |  |
| Sorcerian (J) | 512 KB | `A143A8C5` | standard routine rearranged in place |  |
| South Island Adventure v0.3 | 577232 bytes | `CED56180` | standard routine rearranged in place |  |
| Space Turtleship (K) | 512 KB | `A7255BA8` | standard routine rearranged in place |  |
| Speed Ball 2 - Brutal Deluxe (JU) [c][!] | 512 KB | `9FC340A7` | 4 read(s) with a wait routine |  |
| Star Cruiser (J) | 512 KB | `2B75B52F` | 2 read(s) with a wait routine |  |
| Steel Empire, The (UE) [!] | 1 MB | `D0E7A0B6` | 2 read(s) with a wait routine |  |
| Steel Talons (JUE) (Jun 1993) [!] | 512 KB | `04F388E6` | 2 read(s) with a wait routine |  |
| Steel Talons (UJE) (Jul 1992) [!] | 512 KB | `10E4EC63` | 2 read(s) with a wait routine |  |
| Street Fighter 2 Plus Champion Edition (J) [!] | 3 MB | `2E487EE3` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Street Fighter 2 Special Champion Edition (E) [!] | 3 MB | `56D41136` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Street Fighter 2 Special Champion Edition (U) [!] | 3 MB | `13FE08A1` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Street Smart (JU) [!] | 512 KB | `B1DEDFAD` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| street_fighter2_turbo | 3 MB | `4ACEE0FE` | 4 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Streets of Rage 2 (JE) [!] | 2 MB | `42E3EFDC` | 2 read(s) with a wait routine |  |
| Streets of Rage 2 (U) [!] | 2 MB | `E01FA526` | 2 read(s) with a wait routine |  |
| Strider (UE) [!] | 1 MB | `B9D099A4` | 2 read(s) with a wait routine |  |
| Strider Hiryuu (J) [!] | 1 MB | `859173F2` | 2 read(s) with a wait routine |  |
| Sub-Terrania (E) [!] | 2 MB | `E8CED28D` | 28 read(s) with a wait routine; some reads left alone (no port address nearby) | For the de-interleaved (non-SMD) ROM |
| Sub-Terrania (U) [!] | 2 MB | `DC3C6C45` | 28 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Summer Challenge (JUE) [!] | 2 MB | `D7D53DC1` | 3 read(s) with a wait routine |  |
| Sunset Riders (E) [!] | 512 KB | `0FF33054` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Sunset Riders (U) [!] | 512 KB | `AC30C297` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Super 1998 Sonic 6 (Unl) [c][!] | 2 MB | `04F0C93E` | 2 read(s) with a wait routine |  |
| Super Airwolf (J) | 512 KB | `FA451982` | standard routine rearranged in place |  |
| Super Baseball 2020 (UJ) [R-Jap] | 2 MB | `2BBEE127` | 2 read(s) with a wait routine |  |
| Super Battle Tank - War in the Gulf (U) [!] | 512 KB | `B0B5E3C9` | standard routine rearranged in place |  |
| Super Fantasy Zone (E) [!] | 1 MB | `927975BE` | standard routine rearranged in place |  |
| Super Fantasy Zone (J) [!] | 1 MB | `767780D7` | standard routine rearranged in place |  |
| Super Hang-On (JUE) (REV 00) [R-Eur] | 512 KB | `CB2201A3` | 2 read(s) with a wait routine |  |
| Super Hang-On (JUE) (REV 01) [!] | 512 KB | `3877D107` | 2 read(s) with a wait routine |  |
| Super HQ (JUE) | 512 KB | `AB2C52B0` | standard routine rearranged in place |  |
| Super Hydlide (E) [!] | 512 KB | `1FE2D90B` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Super Hydlide (U) [!] | 512 KB | `1335DDAA` | standard routine rearranged in place; 1 read(s) with a wait routine |  |
| Super Real Basketball (E) [!] | 512 KB | `74DB1377` | standard routine rearranged in place |  |
| Super Real Basketball (JU) [c][!] | 512 KB | `4346E11A` | standard routine rearranged in place |  |
| Super Shinobi II, The (J) | 1 MB | `5B412816` | 8 read(s) with a wait routine |  |
| Super Shinobi II, The (Jap Beta) | 1 MB | `C47E8AEA` | 8 read(s) with a wait routine |  |
| Super Volleyball (U) [c][!] | 256 KB | `A88FEE44` | standard routine rearranged in place |  |
| super_hangon | 512 KB | `76F7EE54` | 2 read(s) with a wait routine |  |
| superbike | 1 MB | `D3AB7F21` | 6 read(s) with a wait routine |  |
| Superman (E) | 1 MB | `7DB434BA` | standard routine rearranged in place |  |
| Superman (U) [!] | 1 MB | `543A5869` | standard routine rearranged in place |  |
| Syd of Valis (U) [!] | 512 KB | `37DC0108` | standard routine rearranged in place |  |
| Syura no Mon (J) | 1 MB | `E19DA6E5` | standard routine rearranged in place |  |
| Taiga Drama Taiheiki (J) | 1 MB | `09FBB30E` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Taikou Risshiden (J) | 1280 KB | `F96FE15B` | standard routine rearranged in place |  |
| Talmit's Adventure (E) | 1 MB | `05DC3FFC` | standard routine rearranged in place |  |
| Target Earth (U) [!] | 512 KB | `CDDF62D3` | standard routine rearranged in place |  |
| Task Force Harrier EX (J) | 1 MB | `E9A54EED` | standard routine rearranged in place |  |
| Task Force Harrier EX (U) [!] | 1 MB | `C8BB0257` | standard routine rearranged in place |  |
| Techno Clash (UEJ) [!] | 1 MB | `4E65E483` | 3 read(s) with a wait routine |  |
| Tecmo Super Baseball (U) [!] | 1 MB | `227A1178` | 18 read(s) with a wait routine |  |
| Tecmo World Cup 92 (JU) [!] | 256 KB | `5E93C8B0` | standard routine rearranged in place |  |
| Tecmo World Cup 93 (JU) [!] | 256 KB | `CAF8EB2C` | standard routine rearranged in place |  |
| Teenage Mutant Hero Turtles - The Hyperstone Heist (E) | 1 MB | `966D5286` | standard routine rearranged in place |  |
| Teenage Mutant Ninja Turtles - Return of the Shredder (J) | 1 MB | `1B003498` | standard routine rearranged in place |  |
| Teenage Mutant Ninja Turtles - The Hyperstone Heist (U) [!] | 1 MB | `679C41DE` | standard routine rearranged in place |  |
| Telebradesco Residencia (JUE) | 256 KB | `1DB99045` | 1 read(s) with a wait routine |  |
| Tetris (JU) | 256 KB | `4CE90DB0` | standard routine rearranged in place |  |
| The Hybridization Project | 1354487 bytes | `BAD8E068` | standard routine rearranged in place |  |
| Theme Park (F) [!] | 2 MB | `289DA2C5` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Theme Park (U) | 2 MB | `D9086BFA` | 1 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Thomas the Tank Engine and Friends (U) [c][!] | 1 MB | `1A406299` | 2 read(s) with a wait routine |  |
| Thunder Fox (U) [c][!] | 1 MB | `5463F50F` | standard routine rearranged in place |  |
| Tiger Hunter Hero Novel (Chinese) | 2 MB | `61E458C3` | standard routine rearranged in place |  |
| Time Dominator 1st (JUE) | 1 MB | `7EBA7A5C` | standard routine rearranged in place |  |
| Tinhead (U) [!] | 1 MB | `D6724B84` | standard routine rearranged in place; 2 read(s) with a wait routine |  |
| Tiny Toon Adventures - Acme All Stars (E) | 1 MB | `1227B2B2` | 3 read(s) with a wait routine |  |
| Tiny Toon Adventures - Acme All Stars (UJ) [!] | 1 MB | `2F9FAA1D` | 3 read(s) with a wait routine |  |
| Tiny Toon Adventures - Buster's Hidden Treasure (E) [!] | 512 KB | `D10FBA51` | standard routine rearranged in place |  |
| Tiny Toon Adventures - Buster's Hidden Treasure (U) [!] | 512 KB | `A26D3AE0` | standard routine rearranged in place |  |
| Todd's Adventures in Slime World (J) | 512 KB | `90C94552` | 2 read(s) with a wait routine |  |
| Todd's Adventures in Slime World (U) | 512 KB | `652E8B7D` | 2 read(s) with a wait routine |  |
| Toki - Going Ape Spit (UE) | 512 KB | `5BBDE6C2` | 2 read(s) with a wait routine |  |
| Toki - Going Ape Spit (UE) [c][!] | 512 KB | `7362C3F4` | 2 read(s) with a wait routine |  |
| Top Pro Golf (J) | 1 MB | `62BAD606` | 2 read(s) with a wait routine |  |
| Top Pro Golf 2 (J) | 1 MB | `B8CE98B3` | 2 read(s) with a wait routine |  |
| Toughman Contest (UEJ) [!] | 4 MB | `E19FBC93` | 2 read(s) with a wait routine |  |
| Toys (U) | 1 MB | `CBC9951B` | standard routine rearranged in place |  |
| Trampoline Terror! (U) [!] | 256 KB | `AABB349F` | 2 read(s) with a wait routine |  |
| Traysia (U) [!] | 1 MB | `96184F4F` | standard routine rearranged in place |  |
| Triple Play 96 (F) [c][!] | 4 MB | `F1748E91` | 7 read(s) with a wait routine |  |
| Triple Play Gold (4) [c][!] | 4 MB | `BBE69017` | 7 read(s) with a wait routine |  |
| True Lies (F) [!] | 2 MB | `18C09468` | 10 read(s) with a wait routine |  |
| Turma da Monica na Terra Dos Monstros (UE) [!] | 1 MB | `F8288DE1` | 2 read(s) with a wait routine |  |
| Twinkle Tale (J) | 1 MB | `D757F924` | 3 read(s) with a wait routine |  |
| Two Crude Dudes (MK-1141) (J) | 1 MB | `B6D90A10` | standard routine rearranged in place |  |
| Two Crude Dudes (T-13026) (J) [R-JAP][!] | 1 MB | `AFFB4B00` | standard routine rearranged in place |  |
| Two Crude Dudes (T-13026) (J) [R-USA][!] | 1 MB | `721B5744` | standard routine rearranged in place |  |
| Ultimate Qix (JUE) [!] | 256 KB | `D83369D9` | standard routine rearranged in place |  |
| Ultimate Soccer (E) [!] | 1 MB | `83DB6E58` | 2 read(s) with a wait routine |  |
| Ultraman (J) | 512 KB | `83B4D5FB` | standard routine rearranged in place |  |
| Uncharted Waters (U) [!] | 1 MB | `4EDAEC59` | standard routine rearranged in place |  |
| Uncharted Waters 2 - New Horizons (U) [!] | 2 MB | `EAD69824` | 5 read(s) with a wait routine |  |
| Universal Driver Demo V4.0 (JUE) [c][!] | 384 KB | `4A1B3DAA` | 2 read(s) with a wait routine |  |
| Urban Strike (UEJ) [!] | 2 MB | `CF690A75` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Valis (J) | 1 MB | `24431625` | 2 read(s) with a wait routine |  |
| Valis (U) [!] | 1 MB | `13BC5B72` | 2 read(s) with a wait routine |  |
| Valis III (J) | 1 MB | `4D49A166` | standard routine rearranged in place |  |
| Valis III (U) [!] | 1 MB | `59A2A368` | standard routine rearranged in place |  |
| Valis SD (J) [!] | 512 KB | `1AEF72EA` | standard routine rearranged in place |  |
| Vapor Trail (J) | 1 MB | `83B6B6BA` | standard routine rearranged in place |  |
| Vapor Trail (U) [!] | 1 MB | `C49E3A0A` | standard routine rearranged in place |  |
| Vectorman (F) (Pre-Release) | 2 MB | `2084D3DA` | 20 read(s) with a wait routine |  |
| Vectorman (F) [!] | 2 MB | `D38B3354` | 20 read(s) with a wait routine |  |
| Vectorman (U) | 2 MB | `63028820` | 20 read(s) with a wait routine |  |
| Vectorman 2 (F) [!] | 3 MB | `C1A24088` | 20 read(s) with a wait routine |  |
| Vectorman 2 (U) | 3 MB | `8569B30D` | 20 read(s) with a wait routine |  |
| Vehicle | 128 KB | `726A41DC` | 1 read(s) with a wait routine |  |
| Verytex (J) [c][!] | 512 KB | `BAFC375F` | standard routine rearranged in place |  |
| Viewpoint (U) [!] | 2 MB | `59C71866` | 4 read(s) with a wait routine |  |
| Virtua Racing (E) [!] | 2 MB | `9624D4EF` | 1 read(s) with a wait routine |  |
| Virtua Racing (U) | 2 MB | `7E1A324A` | 1 read(s) with a wait routine |  |
| Virtual Bart (JUE) | 2 MB | `E2ED7CA9` | standard routine rearranged in place |  |
| Virtual Bart (JUE) [!] | 2 MB | `8DB9F378` | standard routine rearranged in place |  |
| Virtual Pinball (UEJ) [!] | 1 MB | `D63473AA` | 2 read(s) with a wait routine |  |
| Vixen 357 (J) | 1 MB | `3AFA2D7B` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Vixen 357 (U) | 1 MB | `8A4D9AB3` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Volfied (JUE) | 256 KB | `B0C5E3F7` | standard routine rearranged in place |  |
| Wacky Worlds (UEJ) [!] | 1 MB | `8AF4552D` | 10 read(s) with a wait routine |  |
| Waialae Golf (J) [!] | 1536 KB | `CBE2C1F6` | 2 read(s) with a wait routine |  |
| Wani Wani World (J) [c][!] | 512 KB | `56F0DBB2` | standard routine rearranged in place |  |
| Wardner (U) [!] | 512 KB | `1E369AE2` | standard routine rearranged in place |  |
| Wardner Special (J) [!] | 512 KB | `80F1035C` | standard routine rearranged in place |  |
| Warpspeed (JUE) [!] | 2 MB | `143697ED` | 3 read(s) with a wait routine |  |
| Warrior of Rome (U) [!] | 1 MB | `5BE10C6A` | 2 read(s) with a wait routine |  |
| Warrior of Rome 2 (A) [c][!] | 1 MB | `CD8C472A` | 2 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Warsong (U) [!] | 512 KB | `4B680285` | standard routine rearranged in place |  |
| Waterworld (E) | 2 MB | `51C80498` | 4 read(s) with a wait routine |  |
| Wayne Gretzsky NHLPA All-Stars (C) [!] | 2 MB | `C2C13B81` | 5 read(s) with a wait routine |  |
| We're Back! - A Dinosaur's Tale (U) [!] | 1 MB | `70155B5B` | 2 read(s) with a wait routine |  |
| Whac-A-Critter (Unl) [!] | 512 KB | `1BDD02B8` | 2 read(s) with a wait routine |  |
| Wheel of Fortune (U) [!] | 512 KB | `C8D8EFC3` | 4 read(s) with a wait routine |  |
| Where in the World is Carmen Sandiego (U) | 1 MB | `EEF372E8` | 1 read(s) with a wait routine |  |
| Where in Time is Carmen Sandiego (U) [!] | 1 MB | `EA19D4A4` | 1 read(s) with a wait routine |  |
| Whip Rush 2222 AD (J) | 512 KB | `8084B4D1` | standard routine rearranged in place |  |
| Whip Rush 2222 AD (U) [!] | 512 KB | `7EB6B86B` | standard routine rearranged in place |  |
| Wimbledon Championship Tennis (E) [!] | 1 MB | `B791A435` | 5 read(s) with a wait routine |  |
| Wimbledon Championship Tennis (U) [!] | 1 MB | `F9142AEE` | 5 read(s) with a wait routine |  |
| Wings of Wor (U) [!] | 512 KB | `210A2FCD` | standard routine rearranged in place |  |
| Wonder Boy III - Monster Lair (JUE) [c][!] | 512 KB | `C24BC5E4` | standard routine rearranged in place |  |
| Wonder Boy In Monster World (UE) [!] | 768 KB | `1592F5B0` | 2 read(s) with a wait routine |  |
| Wonder Boy V - Monster World III (J) [!] | 640 KB | `45A50F96` | 2 read(s) with a wait routine |  |
| Wonder Library (J) [!] | 512 KB | `9350E754` | standard routine rearranged in place |  |
| World Championship Soccer 2 (U) [!] | 1 MB | `C1DD1C8E` | 4 read(s) with a wait routine |  |
| World Series Baseball 95 (U) [!] | 3 MB | `25130077` | 5 read(s) with a wait routine |  |
| World Series Baseball 96 (F) [!] | 3 MB | `04EE8272` | 5 read(s) with a wait routine |  |
| World Series Baseball 98 (F) [!] | 3 MB | `05B1AB53` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| World Series Baseball 98 (U) | 3 MB | `417A58D6` | 5 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| World War 2 (J) | 1 MB | `B0416C60` | standard routine rearranged in place |  |
| X Dazedly Ray (J) [!] | 512 KB | `AB22D002` | 2 read(s) with a wait routine |  |
| X-Band Modem BIOS - Game Toshokan (J) [!] | 128 KB | `C185C819` | standard routine rearranged in place |  |
| X-Men 2 - Clone Wars (JEU) [!] | 2 MB | `710BC628` | 8 read(s) with a wait routine; some reads left alone (no port address nearby) |  |
| Xenon 2 Megablast (E) [c][!] | 512 KB | `59ABE7F9` | 2 read(s) with a wait routine |  |
| XZR (J) | 1 MB | `880BF311` | standard routine rearranged in place |  |
| Ya-Se Chuan Shuo (Chinese) | 2 MB | `095B9A15` | standard routine rearranged in place; some reads left alone (no port address nearby) |  |
| Yang Warrior Family, The (Chinese) | 2 MB | `6604A79E` | standard routine rearranged in place |  |
| Young Indiana Jones - Instrument of Chaos (J) [!] | 1 MB | `FE8FF938` | 2 read(s) with a wait routine |  |
| Young Indiana Jones - Instrument of Chaos (U) [!] | 1 MB | `4E384EF0` | 2 read(s) with a wait routine |  |
| Young Indiana Jones Chronicles (U) | 512 KB | `44F6BE35` | 1 read(s) with a wait routine |  |
| Ys III - Wanderers from Ys (J) | 1 MB | `52DA4E76` | standard routine rearranged in place |  |
| Ys III - Wanderers from Ys (U) [!] | 1 MB | `EA27976E` | standard routine rearranged in place |  |
| Zan Yasha Enbuden (J) [!] | 512 KB | `637FE8F3` | standard routine rearranged in place |  |
| Zero Tolerance (JUE) [!] | 2 MB | `23F603F5` | 10 read(s) with a wait routine |  |
| Zoom (JU) [!] | 256 KB | `724D6965` | standard routine rearranged in place |  |
| Zoop (4) [!] | 512 KB | `A899BEFA` | 3 read(s) with a wait routine |  |
| Zoop (8) [!] | 512 KB | `2FDAC6AB` | 3 read(s) with a wait routine |  |
