# Pluto

A lightweight, terminal-based text editor that uses familiar keyboard shortcuts instead of modal editing.

## Overview

Pluto is designed to provide an intuitive editing experience using standard keyboard shortcuts (Ctrl+C, Ctrl+V, Ctrl+S, etc.) that users are already familiar with from modern GUI editors. Unlike vim's modal approach, Pluto lets you start typing immediately without learning new editing paradigms.

## Features

- **Standard text editing** - Insert, backspace, delete
- **Navigation** - Arrow keys, mouse click positioning, word-by-word movement
- **File operations** - Open, save, save as
- **Search** - Find text with highlighting, search and replace
- **Clipboard** - Copy, cut, paste with Ctrl+C/X/V
- **Selection** - Select text with Shift+arrows, select all with Ctrl+A
- **Row operations** - Delete entire row, copy entire row
- **Auto-indentation** - Configurable tab width with automatic indentation
- **Terminal support** - Handles terminal resizing, scrolling for large files

## Installation

### Dependencies

Install the ncurses library:

```bash
# Debian/Ubuntu
sudo apt-get install libncurses5-dev libncursesw5-dev

# macOS (with Homebrew)
brew install ncurses
```

### Build

```bash
make
```

## Usage

```bash
./pluto <filename>
```

### Quick Test

A sample test file is included. To quickly test the editor:

```bash
make
./pluto testfile.txt
```

Then try:
1. Use arrow keys to navigate
2. Type some text
3. Press `Ctrl+F` and enter `1` to search, then type `Pluto` to highlight it
4. Press `Ctrl+S` to save (enter a filename when prompted)
5. Press `Ctrl+Q` to quit

### Keybindings

| Key | Action |
|-----|--------|
| Ctrl+Q | Quit |
| Ctrl+O | Open new file |
| Ctrl+S | Save as |
| Ctrl+F | Search / Search and replace |
| Ctrl+C | Copy |
| Ctrl+X | Cut |
| Ctrl+V | Paste |
| Ctrl+A | Select all |
| Ctrl+D | Delete row |
| Ctrl+Y | Copy row |
| Ctrl+R | Move cursor to next word |
| Ctrl+L | Move cursor to previous word |
| Shift+Arrow | Select text |
| Arrow keys | Navigate |
| Mouse click | Position cursor |

## Architecture

Pluto is written in C using the ncurses library for terminal UI.

- **Buffer structure** - Uses a doubly-linked list where each node represents a line of text
- **main.c** - Entry point and input handling loop
- **func.c** - Core editor functionality
- **func.h** - Data structures and function declarations

## License

Open source.
