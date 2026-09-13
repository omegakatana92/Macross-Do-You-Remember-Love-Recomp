# Macross: Do You Remember Love? — PSX Recomp

A work-in-progress native recompilation project for the Japanese PlayStation release of **Chou Jikuu Yousai Macross: Ai Oboete Imasu ka**, commonly known as **Macross: Do You Remember Love?**

This project uses **PSXRecomp** to recompile the original PlayStation executable code for modern systems and uses the current **recomp-ui** launcher.

> **This repository does not contain the game.**
>
> You must provide your own legally obtained copy of **Macross: Do You Remember Love?** to use this project.

## Project Status

**Status: Work in Progress**

This is a **two-disc PlayStation game**. The two discs boot different PlayStation executables:

| Disc | Boot Executable |
| --- | --- |
| Disc 1 | `SLPS_020.05` |
| Disc 2 | `SLPS_020.06` |

Because of this, Macross is more complicated than a multi-disc game where both discs share the same executable. The repository contains discovery information and function seeds for both discs, but complete two-program runtime support still requires additional development and testing.

Do not consider the recomp complete or fully playable yet.

## Framework and New UI

The project pins **PSXRecomp** and **recomp-ui** as Git submodules:

```text
psxrecomp/
recomp-ui/
```

After cloning, initialize them with:

```bash
git submodule update --init --recursive
```

The new recomp-ui is intended to provide first-run setup, disc verification and selection, controller/settings access, Generate & Build functionality, and launching the recomp.

## Two-Disc Support

Users will eventually need to provide both discs from their own legally obtained copy. The repository contains only technical metadata needed for identification and recompilation, such as disc fingerprints, hashes, serial information, executable identity, track information, symbols, and function-discovery seeds.

Disc 1 currently uses `SLPS_020.05`. Disc 2 uses `SLPS_020.06`, with its additional function discovery data stored in:

```text
seeds/ghidra_funcs_disc2.txt
```

Successful recompilation of Disc 1 does **not** automatically mean Disc 2 is supported. The real Disc 1 → Disc 2 transition must also be tested before the project can be considered multi-disc functional.

## Building

Requirements may include Git, Python, CMake, Ninja, a supported C/C++ compiler, and the PSXRecomp dependencies.

Clone the repository recursively, or initialize its submodules after cloning:

```bash
git submodule update --init --recursive
```

A typical development build uses CMake and Ninja:

```bash
cmake -S . -B build -G Ninja
cmake --build build
```

The exact workflow may change as PSXRecomp continues to evolve.

## Providing the Game

You must provide your own legally obtained Japanese PlayStation copy of **Chou Jikuu Yousai Macross: Ai Oboete Imasu ka**. Both discs are required for complete multi-disc testing.

This repository intentionally does **not** provide or redistribute:

- `.bin`, `.cue`, `.iso`, `.chd`, or ROM images
- PlayStation BIOS dumps
- extracted PlayStation game executables
- FMV, music, sound, textures, models, or other copyrighted game assets
- prebuilt `.exe` or `.dll` game binaries
- build directories or generated binary output

No game download is provided. Users must supply their own copy.

## Repository Policy

Do not submit copyrighted game material to this repository. Disc images, ROMs, BIOS files, extracted game assets, executables, DLLs, and build output must not be committed. The project's `.gitignore` contains additional protections against accidentally adding these files.

## Included Development Files

The public repository contains recompilation source/configuration material such as:

```text
CMakeLists.txt
game.toml
game_options.toml
catalog_identity.json
disc_probe.json
symbols.toml
psx_symbols.h
codegen_setup.c
codegen_setup.h
seeds/
tools/
psxrecomp/
recomp-ui/
```

`psxrecomp/` and `recomp-ui/` are Git submodules, not copied framework source trees.

## Function Discovery

Initial function discovery information is stored in:

```text
seeds/ghidra_funcs.txt
seeds/ghidra_funcs_disc2.txt
```

These lists may grow as runtime testing discovers indirect calls, dynamic dispatch targets, overlays, or other executable code.

## Current Development Goals

Current work focuses on getting Disc 1 reliably generated and compiled, reaching gameplay, testing audio/video/input, identifying missing function dispatches and dynamically loaded code, recompiling Disc 2's `SLPS_020.06`, integrating both executable programs, validating the new recomp-ui multi-disc workflow, testing memory-card progression, and reproducing the original Disc 1 → Disc 2 transition.

## Project Completion Definitions

**Buildable** means the recompilation project successfully generates and compiles. **Bootable** means the recompiled game reaches startup/title. **Playable** means actual gameplay can be reached with functioning input. **Multi-disc functional** means both discs are recognized and the game's real Disc 1/Disc 2 progression works. **Complete** means both discs have undergone substantial testing without known game-breaking recompilation problems.

## Credits

### mstan — PSXRecomp

Special thanks and full credit to **mstan** for creating and developing **PSXRecomp**, the PlayStation static recompilation tool and framework that makes this project possible.

**Macross: Do You Remember Love? Recomp would not exist without mstan's work on PSXRecomp.** His work on PlayStation recompilation, code generation, runtime support, and the surrounding tooling provides the technical foundation for this project.

PSXRecomp: https://github.com/mstan/psxrecomp

Additional thanks to everyone who has contributed to PSXRecomp, **RetroPortingToolKit**, and **recomp-ui** as these projects continue to develop.

recomp-ui: https://github.com/RetroPortingToolKit/recomp-ui

## Disclaimer

This is an unofficial fan preservation and technical research project. It is not affiliated with, sponsored by, or endorsed by the owners or publishers of Macross, Sony Interactive Entertainment, mstan, RetroPortingToolKit, or other rights holders and projects mentioned here.

**No copyrighted game files are distributed with this project.**

Users are responsible for providing their own legally obtained copy of **Chou Jikuu Yousai Macross: Ai Oboete Imasu ka (Japan)**, including both discs, in order to use the recompilation project.
