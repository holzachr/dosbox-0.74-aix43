# dosbox-0.74-aix43

An attempt of porting dosbox 0.74 to AIX 4.3.3.

Releases are compiled using xlC 6.0 for small footprint and maximum optimization.

# Prerequisites

Requires SDL-1.2 to run.
You can get it here: https://github.com/holzachr/SDL-1.2.16-aix43

# Installation

Place into /usr/local/bin or whereever you feel is right.

# Optimizing performance

To enable the MIT-SHM X11 extension for fast shared memory, you have to 
```
export DISPLAY=:0.0
export EXTSHM=on
```
before launching the executable.

Using the SDL driver for the Ultimedia Services (UMS) instead of direct audio seems to make use of the sound card's DMA capability:
```
export SDL_AUDIODRIVER="UMS"
run_ums dosbox
```

# License
Check the contained COPYING file for the authors' rights.
