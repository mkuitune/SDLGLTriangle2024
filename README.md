# SDLGLTriangle2024
A sample how to setup a minimal fuzz OpenGL C++ project for windows in 2024.

# Usage
git submodule update --init
cd vcpkg
./bootstrap-vcpkg.sh -useSystemBinaries
cd ..
./vcpkg/vcpkg install --triplet x64-windows
cmake -S . -B build
cmake --build build


# The recipe starting from scratch:

## Step 1

### Prerequisities
Install Git and Cmake and Visual Studio 2022 (Community edition is just fine). Visual Studio comes with Git and CMake so it might suffice (my setup is so messed up I can't tell, sorry).

### Already done in this repo
git init
git submodule add https://github.com/microsoft/vcpkg.git

### Stuff that needs to be done

git submodule update --init

#### posix
cd vcpkg
./bootstrap-vcpkg.sh -useSystemBinaries

#### win
cd vcpkg
bootstrap-vcpkg.bat

## Step 2
run vcpkg install (in project root):
### Windows
./vcpkg/vcpkg install --triplet x64-windows

### Linux
Haven't tested yet

## Step 3 Build
### Command line
cmake -S . -B build
cmake --build build
### Visual studio (2022 and up)
Open CMake project, point it at the CMakeLists.txt file
