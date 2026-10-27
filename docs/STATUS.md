# Status and known limitations

[Back to the project](../README.md)

## Development status

**Experimental.** Testing has been performed on the development PS5. Full-campaign coverage and compatibility across firmware/loader combinations remain outstanding.

The repository is a documentation landing page at present. No binary release, ZIP, game files, keys or private source inputs have been uploaded.

## Verified locally

- Native boot and textured opening gameplay.
- Full base + 2.0.0 update preparation, integrity verification and detection after relaunch.
- Interrupted preparation recovery using authenticated output blocks.
- Approximately 59.9–60 FPS during the tested opening battle at internal 1920×1080 with 3840×2160 output.
- Full 86.471-second opening WebM and its transition to the following real-time scene.
- Saving/loading, as confirmed by the tester.
- Graphics settings save/reload, cancel/default behavior and a counter that measures game frames.
- Packed RomFS overlays for PlayStation prompts and graphics AA/blur settings.

## Known limitations

- The full campaign, later movies and extended play sessions have not been comprehensively tested.
- Shader and pipeline compilation can cause frame-time spikes.
- Higher resolution and FPS targets are selectable; reaching them throughout the game is not established.
- Pre-rendered movies retain their source resolution and frame rate.
- XCI, NSZ and XCZ input containers are unsupported.
- First-time preparation requires an ELF loader on port 9021.
- FSR 3, DLSS and frame generation are unavailable.
- Native Exit produced a teardown SIGSYS diagnostic during testing. The process closed and saved settings survived relaunch, but clean shutdown still needs investigation.
- The new touchpad Select/Minus mapping needs a dedicated physical-controller check after relaunch.

### Fonts and build dependencies

The private build uses Segoe UI font copies from the developer's Windows installation. These need replacement with fonts intended for redistribution.

The PS5 build also references local dependency trees, generated includes and toolchain paths. A clean-machine build route, pinned dependency versions and complete dependency notices are still needed.

### Wider verification

Before calling the port stable, test clean installation on another setup, establish firmware/loader compatibility, verify the touchpad binding physically, investigate Exit, and extend campaign/save compatibility testing.
