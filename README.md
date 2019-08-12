# xtac
This is the source code of the compiler for the **xtab** computer programming language. It contains the compiler source and the standard library.

**xtab** is a low-level general-purpose compiled programming language that is a joy to work in. 

## Compiling `xtac`

### Platform dependencies
`xtac` compiles **xtab** source files into x64 binaries on windows. `xtac` has so far been tested on Windows 10 with no external dependencies other than Windows APIs.

### Downloading
Download the `/source/` folder to your windows machine. The `/source/.bin/` folder contains compiled x64 binaries. The current release of `xtac` is `/source/.bin/xtac.exe`.

### Building
Run the file `/source/.bin/xtac.exe`. This compiles `*.xtab` in the `/source/` folder (and sub-folders) and generates `/source/.bin/xtad.exe`. After resolving **all** issues, rename `xtad.exe` to `xtac.exe` (deleting the existing `xtac.exe` in the process) to have a new release of the `xtac` compiler.
