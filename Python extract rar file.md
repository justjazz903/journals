# Python extract rar file

There are many python modules to deal with the compressed file formats such as `.zip`, `.tar`, `.rar`. The `ZipFile` module and `tarfile` module seems to work with `.zip` and `.tar` files pretty well. However with `.rar` file, the `RarFile` and `patool` module always give me some errors. My guess is that `WinRar` is a paid software so that the algorithms they use are not publicly available so that third party modules might not support it well.

## Prerequisite

1. Have python 3.6+ installed
2. Have WinRar installed
3. Inside a Windows environment (obviously)

## How

Basically we use python's `os` module to directly call the executable `UnRar.exe` inside the WinRar directory. (`UnRar.exe` is installed along with the WinRar software)

Here my WinRar is installed under `C:\Program Files\WinRar`, inside this directory lies the `UnRar.exe` executable file.

Here's an example to extract `C:\Downloads\myfile.rar` to the location folder `C:\Documents\files` using python:

```python
import os

os.system(f"\"C:\Program Files\WinRar\UnRar.exe\" x \"C:\Downloads\myfile.rar\" \"C:\Documents\files\" -y")
```

The python code basically calls the command `"C:\Program Files\WinRar\UnRar.exe" x "C:\Downloads\myfile.rar" "C:\Documents\files" -y` in inside a cmd prompt. 