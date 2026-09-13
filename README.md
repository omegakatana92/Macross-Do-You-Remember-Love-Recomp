# Macross: Do You Remember Love? Recomp

A work-in-progress PlayStation recompilation project for **Chou Jikuu Yousai Macross: Ai Oboete Imasu ka (Japan)** using the RetroPortingToolKit PSXRecomp framework and the current recomp-ui launcher.

## Important

This repository does **not** contain the game.

You must provide your own legally obtained copy of both PlayStation discs in order to generate, build, and play the recomp.

The project intentionally does not distribute:

- `.bin` files
- `.cue` files
- `.iso` / `.chd` disc images
- ROM files
- PlayStation BIOS files
- copyrighted game assets
- extracted game data
- prebuilt game executables
- `build/` output

## Multi-disc game

Macross: Do You Remember Love? is a **two-disc PlayStation title**. Both discs belong to one recomp project.

The project is intended to use PSXRecomp's current multi-disc support together with the modern `recomp-ui` setup/launcher flow.

Users will need their own copies of:

- Disc 1
- Disc 2

The setup process should validate and associate both discs with the same installation.

## Framework

This project targets the current RetroPortingToolKit PSXRecomp layout:

https://github.com/RetroPortingToolKit/psxrecomp

The intended structure uses pinned root-level submodules:

- `psxrecomp/`
- `recomp-ui/`

## Project status

Early development / bring-up.

The project should not be considered complete merely because it compiles. Runtime validation is required for both discs, including:

- boot
- gameplay
- controller input
- audio / XA audio
- FMV playback
- memory-card save/load
- Disc 1 / Disc 2 recognition
- actual disc-transition behavior

## Legal notice

This is an independent fan/technical project. It is not affiliated with or endorsed by the rights holders of Macross, Sony, or the original game publishers/developers.

No copyrighted game content is supplied by this repository. Users are responsible for using legally obtained copies of the original game.
