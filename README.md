# IREE Template CPP

**DISCLAIMER**: This is a first draft which still evolves, as also the CMake configuration in IREE is revised. It is not intended for everyday use and made available without any support.

This template demonstrates how to integrate [IREE](https://github.com/google/iree) into a third-party project with CMake.
IREE runtime support is demonstrated via the `simple_embedding` sample forked from IREE, where the original source can be found [here](https://github.com/google/iree/tree/master/iree/samples/simple_embedding).
The `custom_modules` sample further demonstrates the out-of-tree usage of a custom dialect alongside with the runtime. The original `custom_modules` source can found [here](https://github.com/google/iree/tree/master/iree/samples/custom_dialect).

The template is developed by Marius Brehler at Fraunhofer IML.

## Getting Started

### Prerequisites

Since this template demonstrates how to use IREE compontens out-of-tree, the prerequisites match those of IREE, documented in the [Getting Started on Linux with CMake](https://google.github.io/iree/GetStarted/LinuxCMake) guide.
Make sure you have CMake >= 3.13 and Clang installed. GCC is not fully supported yet.

### Clone and Build
#### Clone

```shell
git clone https://github.com/iml130/iree-template-cpp.git
cd iree-template-cpp
git submodule update --init --recursive
```

#### Configure and Build

```shell
mkdir build
cd build
CC=clang CXX=clang++ cmake -GNinja ..
ninja
```
#### What's next?

Explore the samples `simple_embedding` and `custom_modules` within the build directory:

`simple_embedding`
* `simple_embedding_test`: Test executable.

`custom_modules`
* `custom_modules_test`: Test executable.

`custom_modules/dialect`
* `custom-opt`: See the related documentation for [iree-opt](https://google.github.io/iree/DeveloperOverview#iree-opt) documentation.
* `custom-translate`: See the related documentation for [iree-translate](https://google.github.io/iree/DeveloperOverview#iree-translate) documentation.

Of course you it's also worth to explore the corresponding CMake configuration.
