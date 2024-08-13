# SDLGLTriangle2024
A sample how to setup a minimal fuzz OpenGL C++ project for windows in 2024.


The recipe starting from scratch:
#Step 1

## Already done in this repo
git init
git submodule add https://github.com/microsoft/vcpkg.git

## Stuff that needs to be done

git submodule update --init

### posix
cd vcpkg
./bootstrap-vcpkg.sh -useSystemBinaries

### win
cd vcpkg
bootstrap-vcpkg.bat

# Step 2
in project root:
vcpkg.json:
{
    "version": "3",
    "dependencies": [
        "glm"
    ]
}

# Step 3
run vcpkg install (in project root):
## Windows
./vcpkg/vcpkg install --triplet x64-windows

## Linux
Haven't tested yet

# Step 4 Build
Build it (not sure how much instructions are needed for cmake...)
