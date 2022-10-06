# Build Csmith on Windows

## With Visual Studio

### Prerequisites

We need Visual studio, cmake, and m4 to build Csmith on Windows with Visual Studio.

* **Visual Studio:** Download Visual Studio community edition
[here](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community)
* cmake is now part of Visual Studio ~~**cmake:** Download cmake binary for Windows
[here](https://cmake.org/download/)~~
* m4 is already part of this fork ~~**m4:** Download m4 for Windows
[here](http://gnuwin32.sourceforge.net/packages/m4.htm).
We need the zip files from both "Binaries" and "Dependencies",
and extract `m4.exe` and `regex2.dll` to C:\windows\system32.~~

### Build

Suppose you have cloned the csmith project from
[github](https://github.com/csmith-project/csmith) to c:\csmith. We have
to run cmake to generate Visual Studio solution/projects files, and build them
with Visual Studio.

* Open Visual Studio and click `Tools -> Command Line -> Developer Command Prompt`  
This will open command line.

* Following commands will generate solution/project files with `cmake`. The first output from `cmake`
should indicate the target is Visual Studio.
    ```
    cd c:\csmith
    cmake .
    ```
* Build the solution with Visual Studio by opening the generated `csmith.sln`
and hit `Build -> Build Solution`.

### Binary

EXE binary will be in `src\Debug\` folder.

## With WSL

### Prerequisites

We need WSL, gcc/g++, cmake, and m4 to build csmith with WSL.

* Follow this
[instruction](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
to install WSL (choose Ubuntu as the distro) on Windows.
* Open WSL/Ubuntu terminal window, and run:
    ```bash
    sudo apt install g++ cmake m4
   ```

### Build csmith and optionally install it

This is standard and the same as building/installing csmith on Linux:
```bash
cmake -DCMAKE_INSTALL_PREFIX=<install-prefix> .
make
make install
```