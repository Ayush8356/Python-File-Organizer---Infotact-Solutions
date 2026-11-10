# 🗂️ Python File Organizer

A lightweight command-line script that cleans up a messy folder by sorting files into **Documents**, **Images**, **Videos** and **Others** based on their file extension.

Built as part of my **Python Development Internship at Infotact Solutions** (Jun–Aug 2025).

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)

---

## Overview

Downloads folders and desktops fill up fast. This script scans one target directory, creates category folders, and moves every file into the right one — no third-party libraries, just Python's standard library (`os`, `shutil`).

## Features

- Sorts files by extension (case-insensitive)
- Auto-creates category folders if they don't exist
- Skips sub-directories, only moves files
- Catch-all `Others` category for unrecognised extensions
- Zero dependencies

## Supported Categories

| Folder      | Extensions                                                        |
| ----------- | ----------------------------------------------------------------- |
| `Documents` | `.pdf` `.doc` `.docx` `.txt` `.ppt` `.pptx` `.xls` `.xlsx`        |
| `Images`    | `.jpg` `.jpeg` `.png` `.gif` `.bmp` `.tiff`                       |
| `Videos`    | `.mp4` `.mkv` `.mov` `.avi` `.wmv`                                |
| `Others`    | Everything else                                                   |

Want more types? Add extensions to the `file_types` dictionary in `organize_files.py`.

## How It Works

1. Set `target_directory` to the folder you want to clean.
2. The script creates one sub-folder per category.
3. It loops through every item in the folder and skips directories.
4. Each file's extension is matched against `file_types`, then moved with `shutil.move()`.
5. Anything unmatched goes to `Others`.

## Getting Started

**Requirements:** Python 3.x

```bash
git clone https://github.com/Ayush8356/python-file-organizer.git
cd python-file-organizer
```

Open `organize_files.py` and set your folder path:

```python
target_directory = 'path/target/directory'   # e.g. r'C:\Users\you\Downloads'
```

Run it:

```bash
python organize_files.py
```

> ⚠️ This script **moves** files. Test it on a copy of a folder first.

## Example

**Before**

```
Downloads/
├── resume.pdf
├── holiday.jpg
├── lecture.mp4
├── notes.txt
└── setup.exe
```

**After**

```
Downloads/
├── Documents/
│   ├── resume.pdf
│   └── notes.txt
├── Images/
│   └── holiday.jpg
├── Videos/
│   └── lecture.mp4
└── Others/
    └── setup.exe
```

## Screenshots

<p align="center">
  <img src="Screenshot%202025-07-25%20132710.png" width="45%" />
  <img src="Screenshot%202025-07-25%20132824.png" width="45%" />
</p>

## Project Structure

```
├── organize_files.py                  # main script
├── File Organiser documentation.docx  # project documentation
├── Screenshot 2025-07-25 132710.png
├── Screenshot 2025-07-25 132824.png
└── README.md
```

## Roadmap

- [ ] Take the target folder as a command-line argument (`argparse`) instead of hard-coding it
- [ ] Handle duplicate file names instead of overwriting/failing
- [ ] Add a `--dry-run` mode to preview moves
- [ ] Log every move to a file
- [ ] Load categories from a config file (JSON)

## Author

**Ayush Pal**
B.Tech Information Technology, MAIT Delhi
[GitHub](https://github.com/Ayush8356)
