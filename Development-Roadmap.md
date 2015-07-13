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