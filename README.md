# GNU Radio 4 Block Parser Tool

During the GNU Radio 4 design phase, a macro was invented which was inserted
into the code to enable blocks to self-register in a block registry.

This was done for the purpose of building specific "plugin" shared libraries.
For the purpose of a C++ compiler / preprocessor, the macro evaluates to
nothing; it gets evaluated by an executable tool (this one) at CMake time.

For reasons of avoiding an external build-time dependency, it was avoided to
consider this tool a build-time external dependecy; building it out of the
source tree was instead considered an acceptable step in the CMake process.
(Of course, that is nonsensical: it trades an easy external build-time
dependency for an extremely heavy one, a native-targetting C++ compiler, in the
cross-compiling case.)

This repository contains that tool, extracted from the gnuradio4-core tree.

## Building

This is a CMake project, so building it isn't hard:

```shell
cmake -S ${PATH_TO_CHECKED_OUT_SOURCE} -B build
cmake --build build
```

Of course, seriously, this is a single C++ source file with no external
dependencies, so you might as well manually build it:

```shell
c++ -std=c++23 -o gnuradio_4_0_parse_registrations parse_registrations.cpp
```

