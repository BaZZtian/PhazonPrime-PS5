<p align="center">
  <img src="sce_sys/icon0.png" width="160" height="160" alt="PhazonPrime project icon">
</p>

<h1 align="center">PhazonPrime</h1>

<p align="center">
  <strong>Metroid Prime on PlayStation 5</strong><br>
  An unofficial native PS5 homebrew port based on Metaforce classic, maintained by <a href="https://github.com/BaZZtian">BaZZtian</a>.
</p>

<p align="center">
  <a href="#status-and-availability"><img src="https://img.shields.io/badge/version-v00.001.036-003791" alt="Version00.001.036"></a>
  <img src="https://img.shields.io/badge/platform-PS5%20homebrew-003791" alt="Platform: PS5 homebrew">
  <a href="#requirements"><img src="https://img.shields.io/badge/game%20data-Own%20PAL%20GameCube%20ISO-555555" alt="Game data: Own PAL GameCube ISO"></a>
</p>

<p align="center">
  <a href="#status-and-availability">Status</a> &middot;
  <a href="#installation">Installation</a> &middot;
  <a href="#compatibility">Compatibility</a> &middot;
  <a href="#support">Support</a> &middot;
  <a href="#credits-and-licenses">Credits &amp; licenses</a>
</p>

## About

PhazonPrime adapts the Metaforce classic foundation to a standalone PS5 application,
with graphics through Aurora, Dawn/WebGPU and Mesa/RADV, native audio, DualSense
input and app-local storage. You supply your own supported GameCube disc image.

| Project | Details |
| --- | --- |
| Platform | PlayStation 5 homebrew |
| Original game | Metroid Prime for GameCube |
| Game data | Your own PAL `GM8P01`, revision 0 raw ISO |
| Controller | DualSense |
| Application identity | `PPSA99731` |
| Availability | v00.001.036 publicly available |

## Status and availability

**Install on PS5:** [Download PhazonPrime v00.001.036](https://github.com/BaZZtian/PhazonPrime-PS5/releases/download/v00.001.036/PhazonPrime-v00.001.036-PS5.zip).

| Download | Purpose | Install it? |
| --- | --- | --- |
| `PhazonPrime-v00.001.036-PS5.zip` | PS5 application | Yes |
| `PhazonPrime-v00.001.036-source.zip` | Exact matching source/build material required by component licenses | No |
| `SHA256SUMS` | Text fingerprints for checking download integrity | No |

GitHub's automatic **Source code (zip)** and **Source code (tar.gz)** links are repository snapshots in two formats. They are not additional application builds; the specifically named source ZIP contains the full matching application source. Detailed licensing evidence remains in the separate reference release and is not required for installation.

**Known Issues:** the map has no visible geometry, and some passable doors remain visually closed. See [Known issues](#known-issues).

## Features

| Area | App functionality |
| --- | --- |
| Graphics and audio | Native PS5 rendering, game audio and music |
| DualSense | Movement, right-stick camera input, PlayStation prompts and weapon-selection shortcuts |
| Menus | Save selection, in-game options and a separate Language category |
| Progress | Three regular save slots, station saving and separate optional autosave records |
| System presentation | Tile music generated locally from your own game data |
| Support | A small diagnostic report that you can choose to share manually |

These are the application features. Remaining validation and
reported problems are listed under [Known issues](#known-issues). Full-game
completion, a fixed frame rate and universal firmware support are not claimed.

## Requirements

You need a PS5 configured to run native homebrew, a compatible loader, a way to copy
files and your own supported disc image. No game image, original assets, saves,
firmware or keys are supplied here. Use the PS5 ZIP from the release; this presentation checkout alone is not an installable application.

## Installation

Extract the release PS5 ZIP and copy its `PPSA99731` folder using your compatible homebrew loader. Place your supported raw ISO beside `eboot.bin` as **`owned-pal.iso`**. Close the app before changing files. During updates, replace only shipped app files and preserve your ISO and `userdata/`.

```text
/data/homebrew/PPSA99731/
  eboot.bin
  owned-pal.iso       # Your own supported disc image
  sce_module/
  sce_sys/
  licenses/
  userdata/           # Local saves and settings: preserve during updates
  debug-report.json  # Optional diagnostic attachment for an issue
```

Use the supplied application resources and title identity. Preserve your own local data when updating.

<details>
<summary><strong>First launch and tile music</strong></summary>

The app generates tile music locally from the supported ISO. An internal
completion record tracks successful generation. Interrupted generation retries
on a later launch. Missing generated audio or completion data can be regenerated
while the local ISO remains available.

Leave the application running while the initial local conversion finishes. Closing it can interrupt generation; it retries on a later launch. System-menu tile-music playback has not been verified for this release. No original music is supplied in the download.

</details>

## Compatibility

| Disc profile | Disc ID | Current scope |
| --- | --- | --- |
| PAL / Europe, revision 0 | `GM8P01` | Supported disc profile; full-game progression is not exhaustively validated |
| NTSC-U / North America | Not validated | Untested and currently unsupported |
| NTSC-J / Japan | Not validated | Untested and currently unsupported |

The supported input is a **raw ISO of 1,459,978,240 bytes**. Compressed containers
are unsupported. Recognizing a disc or reaching the title screen does not establish
full gameplay compatibility. No universal PS5 firmware or loader compatibility is
claimed.

## Controls

| DualSense input | Action |
| --- | --- |
| Left stick | Move |
| Right stick | Aim / control the camera |
| Cross | Select / confirm in menus |
| Circle | Back in menus |
| Options | Start / pause; resume from the pause menu |
| Tap and release R1 | Open the map when no weapon shortcut was used |
| Hold R1 + D-pad Up | Power Beam |
| Hold R1 + D-pad Right | Wave Beam |
| Hold R1 + D-pad Down | Ice Beam |
| Hold R1 + D-pad Left | Plasma Beam |

Weapon shortcuts require the corresponding ability in the loaded save. Using a
shortcut consumes the R1 map action, so releasing R1 afterward should not open
the map. Complete physical-controller coverage of all abilities remains open.

### Language

From the save-selection screen, open **Settings**, then the separate **Language**
category. Select a language, choose **Apply & close**, then launch the app again.

The inspected PAL resources offer English, German, French, Spanish, Italian and
Japanese. Full translation and layout coverage remains under review. Japanese
text availability does not imply support for an NTSC-J disc.

## Saves and updates

Use save stations for regular progress and keep an independent backup outside the
app folder. Optional autosave records are separate from the three regular slots;
positional recovery is supported; use regular save stations and keep backups.

- Close PhazonPrime before updating or copying files.
- Preserve **`userdata/`** and your local **`owned-pal.iso`**.
- Back up local data before an update, reinstall or uninstall.
- Different title identities do not automatically share saves. Do not overwrite
  existing data or assume automatic migration from another title identity.
- A full uninstall may remove saves, settings and generated tile music.

No personal saves or prepared test slots are supplied as part of the app.

## Known issues

- **Map:** R1 opens the view, but map geometry is not visible.
- **Doors:** some doors look closed although they can be passed through.

These two defects are planned for later updates. Full-game progression, every ability/language and sustained performance across firmware/loader combinations have not been exhaustively validated. System-menu tile-music playback has not been verified for this release.

## Support

**Help improve PhazonPrime:** report reproducible problems in
[GitHub Issues](https://github.com/BaZZtian/PhazonPrime-PS5/issues). Please write in
English so players and contributors can follow the report.

Include the app version, disc region, selected language, affected room or menu,
reproduction steps, expected behavior and actual result. Include any PS5 error
code and whether the problem occurs consistently.

You may manually attach **`debug-report.json`**, found beside `eboot.bin`. This small
report contains app status and error counters and is designed to exclude saves,
original game data, memory dumps, account identifiers and network addresses.
Review it before sharing. **Nothing is uploaded automatically.** It may not capture
the cause of every crash.

Do not attach your ISO, extracted game files, music, saves, RAM/core dumps,
`private-*` raw logs, credentials or the whole application folder. Remove personal
information from issue text and screenshots.

<details>
<summary><strong>Help with future NTSC support</strong></summary>

If you own an NTSC copy, share its disc ID, region, revision, image format, byte
size and SHA-256 checksum in an issue. On Windows, this PowerShell command reads
your image without changing it:

```powershell
Get-FileHash -LiteralPath 'D:\Games\your-own-copy.iso' -Algorithm SHA256 |
    Select-Object Algorithm, Hash
```

Share metadata only, never the image or extracted files. A hash alone does not
establish compatibility; future support requires validation using owned data
and actual hardware.

</details>

## Credits and licenses

PhazonPrime is an unofficial PS5 homebrew port maintained by **[BaZZtian](https://github.com/BaZZtian)**. It builds on **Metaforce classic** by Axiomatic Data Laboratories and the original Metaforce contributors, including **Jack Andersen** and **Phillip "Antidote" Stephens**. The original authors retain their copyrights and license grants; the PS5 integration does not replace or relicense their work.

### Acknowledgements

- **Metaforce classic:** the engine foundation. Its original copyright notice and historical MIT license are preserved in [Metaforce-MIT.txt](licenses/Metaforce-MIT.txt).
- **Aurora, Dawn/WebGPU, SDL, Mesa/RADV and LLVM:** graphics, platform and runtime technologies developed by their respective contributors.
- **PS5 platform work:** thanks to Mihawk-99, the PS5_Vulkan contributors and the other developers of the open-source PS5 tooling and libraries used or referenced.
- **Input, audio and supporting libraries:** thanks to BlackBearReloaded, the PSGFX and LibAtrac9 contributors, and the respective upstream authors.

Additional component attribution is documented in [NOTICE.txt](NOTICE.txt).

### Licensing

Each component retains its own copyright and applicable license. The original Metaforce MIT license covers the Metaforce material released under that license; it does not automatically cover independent subprojects. PhazonPrime-authored code is covered by its stated license where explicitly indicated, not by a blanket license for the combined application.

The selected v00.001.036 native program uses **MathPhazon (MIT)** and **StoragePhazon (MIT)** instead of the historical original Zeus/Kabufuda implementations. Original Metaforce and third-party grants remain intact; the combined program retains applicable GPLv3 duties. Complete corresponding source is supplied beside the application. See [licensing reference](https://github.com/BaZZtian/PhazonPrime-PS5/releases/tag/licensing-reference-v00.001.000), [replacement provenance](https://github.com/BaZZtian/PhazonPrime-PS5/releases/tag/licensing-reference-v00.001.000), [LICENSE](LICENSE) and [NOTICE.txt](NOTICE.txt).

The DatSketch PS5 model remains separately licensed under CC BY-ND4.0. Its unchanged GLB, attribution, exact conversion source and disclosed runtime representation accompany the release. The license register explains the separate asset terms. See [the dated model conversion assessment](MODEL-LICENSE-ASSESSMENT.md).

### Disclaimer

Metroid Prime and its original game content belong to Nintendo and the respective rights holders. PlayStation and DualSense are trademarks of Sony Interactive Entertainment.

PhazonPrime is an independent, unofficial homebrew project and is not affiliated with or endorsed by Nintendo, Retro Studios, Sony Interactive Entertainment or the original Metaforce developers. No original game data is supplied; users must provide their own supported copy.

## Licensing reference

The [licensing and replacement-provenance reference](https://github.com/BaZZtian/PhazonPrime-PS5/releases/tag/licensing-reference-v00.001.000) records the component matrix, original grants, independent helper replacement and covered input hashes. It is a separate reference download; it is not needed for installation and is not reattached to every application release. Reuse requires unchanged covered inputs/lineage; relevant changes require updated evidence. Each application still supplies its required original notices and matching corresponding source.

This is the curated public distribution repository. Complete matching source accompanies the application release; private development history is retained separately.

## Artwork update — v00.001.036

New project-selected crystalline wayfinder background with the PhazonPrime wordmark replaces the prior Samus background. The original crystal icon is unchanged. The new image is AI-generated project artwork; its source is retained in the matching source ZIP and its origin/limits are in [the artwork notice](licenses/ARTWORK-NOTICE.txt). All original software/model licenses remain unchanged. This artwork/metadata update uses the exact native program from v00.001.035.

**Known issue — system-tile music:** A fresh v00.001.036 PS5 first-load test generated the complete 60-second music file, but automatic publication to registered tile metadata failed again. This release does not fix that path. A one-console manual synchronization was verified separately; audible menu playback still requires an owner hearing check and is not proved by file checks. No game audio is included in the download.

Use **Quick update** in ProsperoStore and retain independent save backups. See [update safety](UPDATE-SAFETY.md) and [release verification](RELEASE-CORRECTION.md). Known map/door-visual issues remain.
