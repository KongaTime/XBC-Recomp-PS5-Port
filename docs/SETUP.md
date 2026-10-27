# Setup and preparation

[Back to the project](../README.md)

These instructions describe the tested local build. **There is currently no installable public download in this repository.** They are provided so players can understand the intended setup.

## Requirements

- A native-homebrew-capable PS5 and compatible mounting/launching setup.
- Your own base Xenoblade Chronicles: Definitive Edition NSP and supported 2.0.0 update NSP.
- Your dumped `prod.keys`. A separate `title.keys` is optional; tickets inside the NSPs are also read.
- An ELF loader on port 9021 while preparing the game.
- About 14.7 GB of free space for prepared output, in addition to any input NSPs stored on the console.

The current importer accepts uncompressed NSP/PFS0 files. Renaming an XCI or compressed NSZ to .nsp does not make it supported. The importer checks the supported executable hashes.

## Installation layout

When a complete build is available, its title folder belongs at:

```text
/data/homebrew/PPSA99426/
  eboot.bin
  sce_module/
  sce_sys/
  launcher/
  xcde.ini
  import/
    base.nsp
    update.nsp
    prod.keys
    title.keys       optional
```

Keep the title ID **PPSA99426**. Mount the complete title folder with a compatible setup; development testing used ShadowMount. Copying this repository's documentation alone does not install the application.

Use the canonical input names above. Original NSP names can also be detected when a search folder has exactly one base-sized NSP and one update-sized NSP.

Alternatively, put the inputs together in a `/Monado/` folder on USB 0 or USB 1. The corresponding native paths are `/mnt/usb0/Monado/` and `/mnt/usb1/Monado/`.

## Prepare and play

1. Copy the input files into the console import folder or supported USB folder.
2. Enable the ELF loader on port 9021.
3. Launch the title and select **Prepare Game** with Cross.
4. Wait while the helper merges the update, writes ExeFS and the packed RomFS, and verifies the output.
5. After successful preparation, the top button changes to **Play**.
6. Select **Play** to launch the game in the same process.

Source NSPs are left unchanged. An already prepared installation is detected on subsequent launches, and its Prepare action is disabled. Triangle has no preparation shortcut.

The ELF loader is required for preparation; launching an already prepared game does not need it.

## Interrupted preparation

The next attempt verifies existing staging blocks and reuses the valid prefix. Incomplete or damaged data is rewritten. Staging is never considered a playable installation; a completed output is activated only after verification.

Prepared output is stored under:

```text
/data/homebrew/PPSA99426/prepared/
  active.txt
  game-*/
    exefs/
    romfs.bin
```

The packed RomFS avoids installing thousands of loose files. Do not edit `active.txt` or rename the active directory while the app is running.

## Saves and settings

The title's writable sandbox contains:

```text
/download0/monado-ps5/save/
/download0/monado-ps5/xcde.ini
```

While the title is running, the tested FTP path is:

```text
/mnt/sandbox/PPSA99426_000/download0/monado-ps5/
```

A sandbox mount may only be visible while the title is running. Close or suspend gameplay safely before copying saves.

Saved preferences override the package's `xcde.ini`. Updating the title folder should preserve application data; uninstalling/deleting the installed app can remove it. Back up saves before changing an installation.

## If preparation fails

Check that the inputs are the supported base game and 2.0.0 update, keys match your dumps, the ELF loader is enabled, and sufficient free space remains. The helper writes a diagnostic log in the title's `import/prepare-helper.log`.

When reporting an error, share the error message and relevant log excerpt after checking it for personal information. Do not upload keys or game files.
