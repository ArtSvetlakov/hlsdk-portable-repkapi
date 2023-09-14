# About
Portable Half-Life SDK fork. I've forked it to obtain a "frozen" copy that can be compiled in Repka Pi without any issues.

Instruction below copied from original repository with some changes (removed all specific platform instructions, also edited link for "git clone" command).


# Half-Life SDK for GoldSource and Xash3D [![Build Status](https://github.com/FWGS/hlsdk-portable/actions/workflows/build.yml/badge.svg?branch=master)](https://github.com/FWGS/hlsdk-portable/actions/workflows/build.yml) [![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/FWGS/hlsdk-portable?svg=true)](https://ci.appveyor.com/project/a1batross/hlsdk-portable)


This repository contains (re-)implementations of some mods as separate branches derived from `master`. The list of supported mods can be found [here](https://github.com/FWGS/hlsdk-portable/wiki/Mods). Note that some branches are unstable and incomplete.

To get the mod branch locally run the following git command:

```
git clone -b <branch> --recursive https://github.com/ArtSvetlakov/hlsdk-portable-repkapi.git
```

</p>
</details>

# Obtaining source code

Either clone the repository via [git](`https://git-scm.com/downloads`) or just download ZIP via **Code** button on github. The first option is more preferable as it also allows you to search through the repo history, switch between branches and clone the vgui submodule.

To clone the repository with git type in Git Bash (on Windows) or in terminal (on Unix-like operating systems):

```
git clone --recursive https://github.com/ArtSvetlakov/hlsdk-portable-repkapi.git
```

# Build Instructions

Building on Debian/Ubuntu aarch64.

### Prerequisites

Install C and C++ compilers (like gcc or clang), cmake and make.

### Building

```
cmake -B build -S .
cmake --build build
```

### Building with waf

To use waf, you need to install python (2.7 minimum)

```
./waf configure -T release
./waf
```

## Build options

Some useful build options that can be set during the cmake step.

* **GOLDSOURCE_SUPPORT** - allows to turn off/on the support for GoldSource input. Set to **ON** by default on Windows and Linux, **OFF** on other platforms.
* **USE_VGUI** - whether to use VGUI library. **OFF** by default. You need to init `vgui_support` submodule in order to build with VGUI.

This list is incomplete. Look at `CMakeLists.txt` to see all available options.

Prepend option names with `-D` when passing to cmake. Boolean options can take values **OFF** and **ON**. Example:

```
cmake .. -DUSE_VGUI=ON -DGOLDSOURCE_SUPPORT=ON -DCROWBAR_IDLE_ANIM=ON -DCROWBAR_FIX_RAPID_CROWBAR=ON
```
