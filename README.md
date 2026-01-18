A concise README.md for the PyQt5 digital clock program with install, run, usage, quick fixes, and troubleshooting.
# Digital Clock (PyQt5)

Simple desktop digital clock built with PyQt5. Displays current time (AM/PM) using a custom 7-seg style font.

## File
- Main script: `digital%20clock%20program.py`  
  Recommended: rename to `digital_clock_program.py` (remove spaces/percent-encoding).

## Requirements
- Python 3.8+
- `PyQt5` package
- Optional: `DS-DIGIT.TTF` font (placed next to the script)

# Run
From the project folder (PowerShell):
.\.venv\Scripts\Activate
python `digital_clock_program.py`
Or run the original filename:
python `digital%20clock%20program.py`

# Usage
The window shows the current time and updates every second.
The program uses DS-DIGIT.TTF if available; otherwise the system fallback font is used.
To switch to 24-hour format, change the time format string in the code (e.g., hh:mm:ss).

# Quick fixes & suggestions
Rename the file to digital_clock_program.py to avoid shell/IDE issues.
Verify font load: check QFontDatabase.addApplicationFont(...) returns a valid id before using it.
Make font size adaptable to window size rather than hardcoding large sizes.
Catch KeyboardInterrupt and other exceptions in startup to exit cleanly or show a message.
Add an --no-font CLI flag to run without requiring the font file for testing.

# Troubleshooting
ModuleNotFoundError: No module named 'PyQt5': run pip install PyQt5 in the active environment.
Missing font / index error: ensure DS-DIGIT.TTF is present or remove font loading code.
Time shows incorrect format: verify the format string passed to QTime.currentTime().toString(...).
Window too small/large: adjust setGeometry(...) or make layout responsive.

# Contributing
Small, focused changes welcome. Test on Windows (PowerShell) and prefer safe filenames (no spaces).

## Install (Windows / PowerShell)
```powershell
python -m venv .venv
.\.venv\Scripts\Activate
pip install --upgrade pip
pip install PyQt5
