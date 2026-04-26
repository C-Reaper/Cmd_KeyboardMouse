# Project README

## Overview
This project is a simple command-line application that demonstrates how to read keyboard and mouse events in C. It uses custom libraries for input handling (`InputKeyboard` and `InputMouse`) and utilizes threading to continuously monitor these inputs.

## Features
- Reads keyboard and mouse events.
- Prints key presses and releases.
- Stops running when 'Q' key is pressed on the keyboard.
- Stops running when left mouse button (button 0) is pressed.

## Project Structure
```
Cmd_KeyboardMouse/
├── build/              # .exe files produced by Main.c
├── libs/               # *.c for bin
├── lib/                # librarys for my own languages
├── code/               # scripts from my custom languages for example .rex, .ll, .omml
├── data/               # Datafile for example .txt or dumped files
├── assets/             # images and sound files
├── src/                # src code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file
└── LICENCE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects (example given WINAPI, X11, ALSA)

## Build & Run
### Linux
To build and run on Linux:
```bash
cd Cmd_KeyboardMouse
make -f Makefile.linux all
./build/Main
```

### Windows
To build and run on Windows:
```bash
cd Cmd_KeyboardMouse
make -f Makefile.windows all
build\Main.exe
```

### Wine
To build and run cross-compiled for Windows on Linux using Wine:
```bash
cd Cmd_KeyboardMouse
make -f Makefile.wine all
WINEPREFIX=~/wine64 WINEARCH=win64 wine build/Main.exe
```

### WebAssembly
To build and run in the browser as a WebAssembly module:
```bash
cd Cmd_KeyboardMouse
make -f Makefile.web all
wasmtime build/Main.wasm
```

Build Options
- `make -f Makefile.(os) all`: Build output.
- `make -f Makefile.(os) do`: Build + executable output.
- `make -f Makefile.(os) clean`: Remove build artifacts.