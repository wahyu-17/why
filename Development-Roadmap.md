# Current Issues

## Proper floating point support

The PS2 has a simplified FPU that doesn't totally respect IEEE-754 and many games depend on accurate implementation of the PS2's FPU to work properly. It's possible to get around many problems using x86's truncate rounding mode and clamping some of the values so that NaNs don't propagate everywhere. On AArch32, rounding mode cannot be changed for multi-data NEON operations and documentation says that AArch64 supports setting rounding mode on multi-data NEON operations, but it still needs to be tested.

A software FPU implementation would fix all of those problems, but it would be pretty slow. There might be a way of detecting places where proper handling of FPU values is needed by using floating point exceptions (which are supported on x86 and ARM) and flagging JIT blocks that need to be re-compiled using software FPU to help with that.

## Speed

### System Memory Mapping

### Improved HLE interrupt handling

### GIF -> GS communication improvements

### Improved code generation

Register allocation needs to be improved, NEON register allocation needs to be enabled on ARM.

### Texture un-swizzling

Would improve games that trash the texture cache a lot (Snowblind games, Xenosaga 2 and probably others)

## IOP (input/output processor)

### Scheduling/timing

Not all kernel functions are implemented, and timing is messy; this causes issues with various games (e.g., "Destroy All Humans!", "Shining Force Neo", "Animaniacs: The Great Edgar Hunt", etc.) and version detection seems to be an issue too.

## VUs (vector units)

### Microprograms/blank screens

There's an issue with the VUs & their microprogram/instruction execution in several different games, resulting in blank screens and similar graphics issues, like character models not showing up in-game. In Final Fantasy X, several scenes are blank upon entering (e.g., Macalania Woods); in Final Fantasy X-2, this happens in several scenes as well. Other games suffer from very similar issues too, I believe (Xenosaga 2, Rugrats: Royal Ransom, Whiplash, etc.). Could be the result of improper memory allocation.