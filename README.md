# Xenoblade Chronicles — PS5 Recomp Port

**A native PS5 port of Monado, the static recompilation of Xenoblade Chronicles: Definitive Edition.**

Maintained by [KongaTime](https://github.com/KongaTime).

> **Status: experimental, in development.** Native gameplay has been tested on a PS5. This repository currently contains the project overview and documentation. No installable build, ZIP, or release binary is published here.

[Setup guide](docs/SETUP.md) · [Controls & graphics](docs/CONTROLS-AND-GRAPHICS.md) · [Status & limitations](docs/STATUS.md) · [Credits](docs/CREDITS.md)

## What the port offers

- Native PS5 gameplay with textured characters, environments, lighting and effects.
- A controller-operated launcher with **Prepare Game / Play**, **Settings** and **Exit**.
- On-console preparation of a base-game NSP and the supported **2.0.0 update**, with integrity verification and interrupted-preparation recovery.
- A **1080p internal resolution / 60 FPS default target**, with additional resolution and frame-rate settings.
- **AMD FSR 1**, **SMAA**, depth-of-field and blur controls, V-Sync and an FPS counter.
- Opening movie playback, saving and loading, and PlayStation button prompts.
- **Cross to confirm**, **Circle to go back**, and **touchpad press for Select / Minus**.

## Current progress

| Area | Current status |
| --- | --- |
| Native boot and textured gameplay | Verified on the development PS5 |
| Base + 2.0.0 preparation | Full extraction, verification and prepared-install detection tested |
| 1080p / 60 FPS | Approximately 59.9–60 FPS recorded in the tested opening battle |
| Opening movie | Full opening movie and transition into real-time gameplay tested |
| Saving and loading | Confirmed by the tester |
| Launcher graphics settings | Save, reload, cancel and defaults tested |
| Full campaign | Not yet verified |
| Public installable download | Not available yet |

The 60 FPS figure describes the tested opening battle, not a guarantee for every area. Shader compilation can cause stutter. Higher rendering resolution uses the original game textures; this is not an HD texture pack.

## What players will need

Once an installable build is available:

- A PS5 setup capable of running native homebrew. Development testing used ShadowMount; a firmware and loader compatibility matrix has not yet been established.
- Their own base-game NSP, the supported **2.0.0 update NSP**, and dumped key files.
- An ELF loader listening on **port 9021** during first-time preparation.
- Approximately **14.7 GB of additional free space** for prepared output, plus any input files kept on the console.

See the [setup guide](docs/SETUP.md) for file names, folder layout and preparation steps. Uncompressed NSP/PFS0 inputs are supported; XCI, NSZ and XCZ are not currently supported.

Other remaining work includes replacing the private Windows font copies, making the build reproducible outside the development machine, and investigating a native Exit teardown error. See [status and limitations](docs/STATUS.md).

## Reporting problems

Use [Issues](https://github.com/KongaTime/XBC-Recomp-PS5-Port/issues) to report reproducible problems. Include the build, PS5 firmware, loader, graphics settings and steps to reproduce. Never attach keys, game dumps or save files containing personal information.

## Credits

This PS5 port builds on **Monado** and **[LASRecomp](https://github.com/peiikai/LASRecomp)** by **Peiikai**, alongside the PS5 homebrew community and the dependencies listed in [Credits](docs/CREDITS.md).

Independent homebrew project. Not affiliated with or endorsed by Nintendo or Monolith Soft. Xenoblade Chronicles and associated game content belong to their respective owners.
