# toolchain-gccmingw32

This is a drop-in replacement for platformio/toolchain-gccmingw32 with a working gdb (no libpython2.7.dll needed).

The build steps are:

* Download `mingw-get-setup.exe` from https://sourceforge.net/projects/mingw/files/Installer/mingw-get/ and run it
* run `mingw-get update`
* run `mingw-get install g++`
* run `mingw-get install gdb`
* delete the contents of `var\cache` to save some space
* increment the last part of the version number in `package.json` for good measure
* zip everything together (package.json must be in the root of the archive, right next to bin, lib, etc.)
* create a release on github and add the .zip-file

To use this toolchain, configure the platform and platform_packages options in your platformio.ini file:

```ini
[env:htl]
platform = windows_x86
platform_packages =
  toolchain-gccmingw32 @ https://github.com/htlweiz/toolchain-gccmingw32/releases/latest/download/toolchain-gccmingw32.zip
```
