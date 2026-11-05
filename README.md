<div align="center">

<img src="launcher/assets/logo-full.png" alt="Dash Client" width="260">

# Dash Client

**A fast, minimal Minecraft: Java Edition client. A from-scratch launcher plus an in-game mod menu, with 17 performance mods built in.**

[![Latest release](https://img.shields.io/github/v/release/bununxd/Dash-Client?include_prereleases&label=release)](https://github.com/bununxd/Dash-Client/releases)
[![Downloads](https://img.shields.io/github/downloads/bununxd/Dash-Client/total)](https://github.com/bununxd/Dash-Client/releases)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](#requirements)
[![License](https://img.shields.io/badge/license-MIT%20%2F%20CC0-green)](#license)

[**Download**](https://github.com/bununxd/Dash-Client/releases) · [Features](#features) · [Build from source](#build-from-source) · [FAQ](#faq)

</div>

<!-- Add a hero screenshot or GIF here, e.g. ![Dash Client](docs/hero.png) -->

> Dash Client is not an official Minecraft product. It is not approved by or associated with Mojang or Microsoft.

## What is it?

Dash Client has two parts that work together:

| Part | What it does |
| --- | --- |
| **Dash Launcher** (`/launcher`) | Electron launcher written from scratch. Handles sign-in, instances, Minecraft + Fabric setup, performance mods, skins, worlds and modpacks. |
| **Dash mod** (`/mod`) | Fabric mod loaded automatically in every instance. Press **Right Shift** in game for the Dash menu: HUD, zoom, freelook and quality-of-life tweaks. |

Press **Play** and the launcher downloads Minecraft, libraries, assets and Java, installs Fabric + Fabric API, adds the performance mods and the Dash mod, then starts the game.

## Features

### Launcher
- **Microsoft sign-in** with multiple saved accounts. Login tokens are encrypted with your OS secure storage and never sent to any Dash server.
- **Instances**: up to 10, each with its own Minecraft version, mods, resource packs, shaders and worlds. Duplicate an instance or export it as a `.mrpack`.
- **Modrinth browser**: search and install mods, resource packs, shaders and modpacks in one click. Required dependencies come along.
- **Modpack import** (`.mrpack`): preview before install, checksum-verified downloads, Fabric packs.
- **17 built-in performance mods**, each with an on/off switch: Sodium, Lithium, FerriteCore, ImmediatelyFast, Entity Culling, Sodium Extra, More Culling, ModernFix, Krypton, Dynamic FPS, ScalableLux, Noisium, BadOptimizations, C2ME, Enhanced Block Entities, MemoryLeakFix, Clumps. Mods without a build for your version are skipped automatically.
- **Worlds**: one-click backups, restore, import, automatic backups before launch.
- **Crash viewer**: reads crash reports and suggests a likely cause (out of memory, wrong Java, mod conflicts, drivers).
- **Skin editor** with a 3D preview, skin library and PNG import/export. Also screenshots tab, server list with live status, per-instance RAM, GUI scale, and a terminal tab with the full launch log.
- **Self-updating**: the launcher and the Dash mod update themselves.

### In-game mod (Right Shift)
A module grid with search, favourites and a settings gear per module. Everything is configured in game, no config files.

| Category | Modules |
| --- | --- |
| **HUD** (all draggable in *Edit HUD Layout*) | FPS, CPS, Ping, Coordinates, Server IP, Compass, Potion effects, Keystrokes, Armor HUD, Spotify player |
| **Visual** | Custom hotbar and XP bar colours, custom crosshair (12 shapes), enchant glint colour, block overlay, Fullbright, Dark Mode, Own nametag |
| **Clear View** | Small totem and shield, low fire, fewer particles, clear screen overlays, thin rain and snow |
| **Camera** | Zoom (hold `C`), Freelook (hold `Left Alt`) |
| **Utility** | Toggle Sprint / Sneak, Discord Rich Presence |

## Screenshots

<!-- Replace with real images in /docs -->
| Home | Instances | In-game menu |
| --- | --- | --- |
| _coming soon_ | _coming soon_ | _coming soon_ |

## Requirements

- Windows 10 or 11
- A Microsoft account that owns **Minecraft: Java Edition** (there is no offline or cracked-account mode)
- Internet access on first launch
- Minecraft 1.19+ for plain instances. The Dash mod itself supports **Minecraft 26.2 and 26.3**.

Java is downloaded for you.

## Install

1. Download `Dash-Client-Setup-<version>.exe` from the [Releases](https://github.com/bununxd/Dash-Client/releases) page.
2. Run it. Windows SmartScreen may warn you because early builds are not code-signed: click **More info > Run anyway**.
3. Sign in with your Microsoft account and press **Play**.

## Build from source

**Launcher** (Node.js 20+):

```bash
cd launcher
npm install
npm start          # run in development
npm run dist       # build the installer into dist/
```

**Mod** (JDK 25):

```bat
cd mod
build.bat build all      :: builds the 26.2 and 26.3 jars into build\libs
build.bat run 26.3       :: test in a dev client
```

Put the built jars in `launcher/mods/` (keep the Minecraft version in the file name, e.g. `dash-client-1.1.7+mc26.3.jar`) so fresh installs start with the newest mod.

## Privacy and security

- Your login token is stored encrypted on your own PC and goes only to Microsoft, Xbox and Minecraft services.
- Mod updates are downloaded only from this repository's Releases and verified by checksum. <!-- Add "and signature" once UPDATE_PUBLIC_KEY is set, see notes -->
- The launcher only talks to Microsoft/Xbox/Mojang, Fabric, Modrinth and this GitHub repository. No analytics or telemetry.
- The in-game **Lyrics** module looks up songs on [lrclib.net](https://lrclib.net) and the media widgets read what Windows is currently playing, only while those modules are on.

## FAQ

**Is it free?** Yes, free and non-commercial.

**Mac or Linux?** Not yet. Windows only for now.

**Will I get banned on servers?** Dash only includes client-side quality-of-life modules and performance mods. Always check a server's own rules before joining.

**Why does Windows warn me?** Early builds are not code-signed yet. Code signing is on the roadmap.

## Roadmap

- [x] Instances, Modrinth browser, modpack import/export
- [x] Crash viewer, world backups, screenshots
- [x] Self-updating launcher and mod
- [ ] Code-signed installer
- [ ] CurseForge modpacks
- [ ] macOS and Linux

## Credits

Built on [Fabric](https://fabricmc.net) and [Modrinth](https://modrinth.com). The bundled performance mods are by their respective authors and keep their own licenses. Minecraft files are downloaded from Mojang and never redistributed.

## License

The launcher is MIT licensed and the Dash mod is CC0. See [`LICENSE`](LICENSE) and [`mod/LICENSE`](mod/LICENSE).

## Contact

Found a bug or have an idea? [Open an issue](https://github.com/bununxd/Dash-Client/issues).
