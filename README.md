# toolchain-gccmingw32

This is a drop-in replacement for platformio/toolchain-gccmingw32 with a working gdb (no libpython2.7.dll needed).

The build steps are:

* Download `mingw-get-setup.exe` from https://sourceforge.net/projects/mingw/files/Installer/mingw-get/ and run it
* run `mingw-get update`
* run `mingw-get install g++`
* run `mingw-get install gdb`
* delete the contents of `var\cache` to save some space
* increment the last part of the version number in `package.json` for good measure

To use this toolchain, configure the platform and platform_packages options in your platformio.ini file:

FIXME: add instructions here
