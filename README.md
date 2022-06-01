<p align="center">
    <img height="300" alt="Logo of the distro" src="artwork/logo.png"/>
</p>

# Gloire

![](artwork/screenshot.png)

Gloire is an OS built with the [Ironclad](https://github.com/streaksu/ironclad)
kernel and using GNU tools for the userland, along with some original
applications like `gwm`. This repository holds scripts and tools to build the
OS from the ground up.

Gloire is named after the [french ironclad](https://en.wikipedia.org/wiki/French_ironclad_Gloire),
which was the first ocean-going vessel of its kind.

## Building

The project uses `jinx` as its build system, which is included in the tree.
The instructions to build are:

```bash
./jinx build-all           # Build all packages.
./build-support/makeiso.sh # Create the image.
```
This commands will generate a bootable disk image that can be burned to
USB mass-storage media or be booted by several emulators, an example to boot
the image with QEMU would be:

```bash
qemu-system-x86_64 -enable-kvm -cpu host -m 2G -smp 4 -hda gloire.iso
```

A list of the tools needed for compilation of the OS are:

- `git` for cloning packages.
- `curl` for downloading tarballs.
- `GNU Bash`.
- A working `docker` install.
- Common UNIX tools like `coreutils`, `grep`, `find`, etc.
- `xorriso` for image building.
- `qemu` for testing, if wanted.

## Thanks to

- [Mintsuki](https://github.com/mintsuki) for the limine bootloader and `jinx`.
- [The managarm project](https://github.com/managarm) for help with some
of the recipes and `mlibc`.
