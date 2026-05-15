# GTK Chess Bot

A GUI-based Chess Game written in C using GTK3, featuring both PvP and vs Computer gameplay modes, complete move validation, check/checkmate detection, custom board rendering, and event-driven interactions.

---

## Features

- ♟️ Complete Chess Gameplay
- 🤖 vs Computer Mode 
- 👥 Player vs Player Mode
- ✅ Legal Move Validation
- ⚠️ Check and Checkmate Detection
- 🎨 Custom GTK3 Chessboard Rendering
- 🖱️ Interactive Mouse-Based Controls
- 🪟 Multiple GUI Windows and Menus
- 🌍 Cross Platform Support (Linux + Windows)

---

## Project Structure

```text
Chess_Game/
│
├── src/
│   ├── mainn.c
│   ├── game.c
│   ├── game.h
│   ├── guii.c
│   ├── guii.h
│   ├── globals.c
│   └── globals.h
│
├── chess_pieces/
│   ├── *.png
│
├── CMakeLists.txt
└── README.md
```

---

## Technologies Used

- C Programming Language
- GTK3
- Cairo Graphics
- GLib
- CMake

---

# Linux (Ubuntu) Setup

## Install Dependencies

```bash
sudo apt update
sudo apt install build-essential cmake libgtk-3-dev pkg-config
```

---

## Build Instructions

```bash
mkdir build
cd build

cmake ..
make
```

---

## Run

```bash
./chessbot
```

---

# Windows Setup (MSYS2 / MinGW64)

## Install MSYS2

Download and install:

https://www.msys2.org/

---

## Install Required Packages

Open **MSYS2 MinGW64 Terminal** and run:

```bash
pacman -Syu
```

Restart terminal and then run:

```bash
pacman -S mingw-w64-x86_64-gcc
pacman -S mingw-w64-x86_64-gtk3
pacman -S mingw-w64-x86_64-cmake
pacman -S make
```

---

## Build Instructions

```bash
mkdir build
cd build

cmake ..
make
```

---

## Run

```bash
./chessbot.exe
```

---

# Important Compatibility Notes

## Linux Compatibility Fix

Linux already contains a standard library function named:

```c
random()
```

So rename this variable:

```c
extern int random;
```

to something else like:

```c
extern int random_mode;
```

throughout the project.

---

## GTK Compatibility Fix

Replace:

```c
G_APPLICATION_DEFAULT_FLAGS
```

with:

```c
G_APPLICATION_FLAGS_NONE
```

for older GTK/GLib compatibility on Ubuntu.

---

## Image Path Compatibility

Windows-style paths such as:

```c
"C:\\msys64\\mingw64\\lib\\chessbot\\..."
```

will not work on Linux.

Use relative paths instead:

```c
"./chess_pieces/"
```

or

```c
"../chess_pieces/"
```

Recommended project structure:

```text
Chess_Game/
├── build/
├── chess_pieces/
└── src/
```

---

# Gameplay Modes

## vs Computer Mode

- Human vs Logic driven Computer mode
- Automatic opponent moves
- Move highlighting

## PvP Mode

- Two-player local gameplay
- Turn-based interactions

---

# Chess Logic Implemented

- Pawn Movement
- Rook Movement
- Bishop Movement
- Knight Movement
- Queen Movement
- King Movement
- Check Detection
- Checkmate Detection
- Move Filtering

---

# Future Improvements

- Better AI using Minimax
- Undo/Redo System
- Castling
- En Passant
- Pawn Promotion GUI
- Sound Effects
- Online Multiplayer
- FEN/PGN Support

---

# Author

Parv Dixit  
Electrical Engineering, IIT Jodhpur

---

# License

This project is open-source and free to use for educational purposes.
