# Pokémon: Legends of the Fallen Eclipse — milestone 1

This is a **separate development branch** from Pokémon: Chaos Eclipse. The expansion's existing Emerald maps and story progression are reused as a provisional prologue; it is **not** a finished new region or complete game.

## Playable in this source milestone

- **Starter selection:** choose Rowlet, Fennekin, or Froakie from Birch's bag on Route 101 (Duskwood Path). The existing engine handles the starter rescue battle.
- **Exploration:** the existing Littleroot / Route 101 / Oldale / Route 102 maps are accessible; the opening town and paths have Fallen Eclipse signs and dialogue.
- **Wild grass encounters:** Route 101 has a curated spooky species pool (Hoothoot, Poochyena, Ralts, Zubat, Murkrow, Shuppet) at the route's existing levels. Other maps retain upstream encounters instead of the Chaos Eclipse 80% full-Dex randomizer.
- **First themed trainer battle:** the Route 102 Bug Catcher Rick slot is now **SHADE**, with level 4 Poochyena and level 5 Shuppet and a short story hint. The overworld trainer sprite/class is still the inherited Bug Catcher placeholder.
- **Story hook:** an eclipse is affecting wild Pokémon, and the old observatory is implicated.

## Build on Windows 10/11 (WSL2 recommended)

1. Install WSL Ubuntu and follow the upstream dependency instructions at [docs/install/windows/WSL.md](docs/install/windows/WSL.md).
2. In Ubuntu, with the GBA toolchain and required build dependencies installed:

```sh
git clone https://github.com/hbtld/pokeemerald-expansion.git
cd pokeemerald-expansion
git switch feature/fallen-eclipse-milestone-1
make -j2
```

3. When compilation succeeds, look for **pokeemerald.gba** at the project root. Rename your *personal* build to `FallenEclipse-M1.gba` if desired.
4. Open your compiled `.gba` in mGBA on Windows. For Manic EMU on iPhone, copy the `.gba` to Files (iCloud Drive / On My iPhone) and import it through Manic EMU's GBA library/import UI. Actual Manic EMU compatibility requires a device test; no iPhone test is claimed.

**Do not distribute Nintendo ROMs or copyrighted assets.** For public releases, distribute a legal patch, document the exact compatible base file and use a patching tool such as Floating IPS.

## Manual QA checklist

- New game begins and the original moving-truck opening can be completed.
- Visit Ashen Glen and Duskwood Path, encounter the professor, inspect three starters.
- Confirm the chosen starter battles the attacking wild Pokémon, then visit the lab.
- Return to Duskwood tall grass to encounter its spooky pool.
- Progress through Oldale, travel west to Umbral Trail (Route 102), and defeat SHADE.
- Save, reset, reload and confirm team and trainer victory persist.
- Test on Windows mGBA and on an actual iPhone Manic EMU install.

## Current limitations

The world layout, several NPCs, story progression, graphics, title screen, and trainer class/sprite remain inherited from Emerald. No fresh map tiles, title graphics, new trainer class, triple battles, or complete new region have been implemented yet. No build or emulator test is asserted unless GitHub CI or a local tester reports success.

## Next milestones

1. Add an original observatory map and event flags.
2. Replace provisional NPC sprites/text and redesign starting-town layouts in Porymap.
3. Add a full story chapter, rival progression, balance pass and public patch pipeline.
