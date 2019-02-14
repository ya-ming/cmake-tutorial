# cmake-tutorial

Learn cmake follows the tutorial at https://cmake.org/cmake-tutorial/

### Build system generation

Generate the build system using [CMake](https://cmake.org/) from the solution root.  For example:

```bash
mkdir build
cd build
cmake -G "Visual Studio 15 2017" -A "x64" ..
```

### Compiling, linking, et cetera

Either use [CMake](https://cmake.org/) or your toolchain's IDE to build.
For [CMake](https://cmake.org/):

```bash
cd build
cmake --build . --config Release
```

### Testing

```bash
cd build
ctest
```

### Step 0

Basic project to build an executable from source code files.

### Step 1

Adding version number and configured header file

### Step 2

Adding a library

### Step 3

Adding tests