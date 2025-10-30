# runpy

Minimal tool to run a Python script with automatic isolated dependencies.

## Usage

```bash
./runpy myscript.py [arguments...]
````

## What it does

1. Parses `myscript.py` to detect imported modules.
2. Optionally reads dependencies from a `requirements.txt` file
   (searched first in the same folder as the script, then in the current working directory).
3. Creates a virtual environment in `.venv-runpy/myscript.py`.
4. Installs all missing dependencies via `pip`.
5. Executes the script inside the isolated environment.

## Requirements

* Python 3.10+
* `pip` installed
* Linux system (tested on Linux Mint)

## Example

```bash
./runpy example.py
```

## Notes

* The virtual environment is reused if it already exists.
* Standard library modules are automatically ignored.
* If `requirements.txt` is present, its dependencies are always installed in addition to detected imports.
* Ideal for testing or running standalone scripts without polluting the system Python.


