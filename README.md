# runpy

Minimal tool to run a Python script with automatic isolated dependencies.

## Usage

```bash
./runpy myscript.py [arguments...]
```

## What it does

1. Parses `myscript.py` to find imported modules.
2. Creates a virtual environment in `.venv-runpy/myscript.py`.
3. Installs missing dependencies via `pip`.
4. Runs the script inside the isolated environment.

## Requirements

- Python 3.10+  
- `pip` installed  
- Linux system (tested on Linux Mint)

## Example

```bash
./runpy example.py
```

## Notes

- The virtual environment is reused if it already exists.
- Standard library modules are not reinstalled.
