# Credits and attribution

[Back to the project](../README.md)

## Project

- **KongaTime** — PS5 port integration, console testing and project maintenance.
- **Monado contributors** — Xenoblade Chronicles: Definitive Edition static recompilation and runtime.
- **Peiikai / [LASRecomp](https://github.com/peiikai/LASRecomp)** — the MIT-licensed recompiler/runtime foundation used by Monado.

## PS5 integration

Startup, linker layout and RADV integration were adapted from the existing The-Darkness-Recomp PS5 port used in development.

Platform, SDL/input adapters and context-switch integration were adapted from the KH 358/2 Days PS5 port and local PS5 homebrew templates, retaining attribution to **Mihawk** for the underlying public PS5 platform work.

## Dependencies used by the development build

- Public PS5 payload SDK and PS5 homebrew platform work.
- SDL3.
- Mesa / RADV, Vulkan headers and loader, Vulkan Memory Allocator, and Volk.
- glslang / SPIR-V tooling.
- Dear ImGui.
- AMD FSR 1 and SMAA.
- FFmpeg, Opus and zlib.
- hactool by SciresM and mbedTLS.
- stb_image.

These projects retain their respective licenses. This documentation page does not distribute their binaries. A future source or binary release must preserve the applicable notices and provide the corresponding build materials where required.

The PlayStation button prompts in the tested port are generated procedurally over the user's game textures; no third-party button icon pack is bundled.

## Game and presentation

Xenoblade Chronicles and associated characters, trademarks, game code and assets belong to their respective owners. This is an independent homebrew project and is not affiliated with or endorsed by Nintendo or Monolith Soft.

Game dumps, keys, translated game code, shader caches, saves, private Windows fonts and the local build's artwork are not included in this repository.
