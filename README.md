# xtac
This is the source code of the compiler for the **xtab** computer programming language. It contains the compiler source and the standard library.

**xtab** is a low-level compiled programming language. 

## Compiling `xtac`

### Platform dependencies
`xtac` compiles **xtab** source files into x64 binaries on windows. On windows, `xtac` has no external dependencies other than the Windows APIs and the C runtime library. `xtac` emits AVX instructions.

### Downloading
Download the `/source/` folder to your windows machine. The `/source/.bin/` folder contains compiled x64 binaries. The current release of `xtac` is `../source/xtac.exe`.

### Building
Run the file `../source/xtac.exe`. This compiles all non-empty `*.xtab` files in the `/source/` folder (and sub-folders) and generates `/source/.bin/xtac.exe`. After resolving **all** issues, copy `/source/.bin/xtac.exe` to `../source/xtac.exe` (deleting the existing `xtac.exe` in the process) to have a new release of the `xtac` compiler.
