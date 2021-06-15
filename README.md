# ultralight-quick-start

__Clone this repo to try a simple Ultralight app!__

This is a minimal Ultralight app you can use with the [Writing Your First App](https://docs.ultralig.ht/docs/writing-your-first-app) article in the Ultralight documentation.

## 1. Install the Prerequisites

Before you build and run, you'll need to [install the prerequisites](https://docs.ultralig.ht/docs/installing-prerequisites) for your platform.

## 2. Clone and build the app

To clone the repo and build, run the following:

```shell
git clone https://github.com/ultralight-ux/ultralight-quick-start
cd ultralight-quick-start
mkdir build
cd build
cmake ..
cmake --build . --config Release
```

> **Note**: _If you run the command cmake .. without any generators on Windows, it will usually select the default 32-bit Visual Studio version you have installed. To force CMake to generate 64-bit projects on Windows, use `cmake .. -DCMAKE_GENERATOR_PLATFORM=x64` instead of `cmake ..`_

> **Note**: _If you run the command cmake .. without any generators on Windows, it may select the 32-bit MSVC toolchain (Ultralight needs the 64-bit MSVC toolchain instead).

To force CMake to generate 64-bit projects instead, use
cmake .. -DCMAKE_GENERATOR_PLATFORM=x64 instead of cmake .._

## 3. Run the app

### On macOS and Linux

Navigate to `ultralight-quick-start/build` and run `MyApp` to launch the program.

### On Windows

Navigate to `ultralight-quick-start/build/Release` and run `MyApp` to launch the program.

## Further Reading

Follow the [Writing Your First App](https://docs.ultralig.ht/docs/writing-your-first-app) guide and other tutorials in the documentation for more info.
