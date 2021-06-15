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


Using the C++ API
SUGGEST EDITS
📘
Need C API Instead?

We also offer an alternative C API for use within C and other languages!

See Using the C API

Set Up Include Directories
To use Ultralight in your C++ code, simply add the following directory to your project's include directories (replace <SDK_ROOT> with the actual path you've placed the SDK):

<SDK_ROOT>/include/
Include Headers In Your Code
Simply include <Ultralight/Ultralight.h> at the top of your code to import the API.

#include <Ultralight/Ultralight.h>
If you want to use the optional AppCore API (cross-platform windowing/drawing layer), you should also include <AppCore/AppCore.h> at the top of your code.

#include <AppCore/AppCore.h>
Ultralight also exposes the full JavaScriptCore API so that users can make native calls to/from the JavaScript VM. To include these headers simply add:

#include <JavaScriptCore/JavaScript.h>

Using the C API
SUGGEST EDITS
In addition to our C++ API, Ultralight also offers a portable C API for use within C and other languages.

Set Up Include Directories
To use Ultralight in your code, simply add the following directory to your project's include directories (replace <SDK_ROOT> with the actual path you've placed the SDK):

<SDK_ROOT>/include/
Include Headers In Your Code
Simply include <Ultralight/CAPI.h> at the top of your code to import the API.

#include <Ultralight/CAPI.h>
If you want to use the optional AppCore API (cross-platform windowing/drawing layer), you should also include <AppCore/CAPI.h> at the top of your code.

#include <AppCore/CAPI.h>
Ultralight also exposes the full JavaScriptCore API so that users can make native calls to/from the JavaScript VM. To include these headers simply add:

#include <JavaScriptCore/JavaScriptCore.h>

Linking to the Library
SUGGEST EDITS
🚧
64-bit Only

We currently only offer 64-bit bins (x86_64 / amd64) at this time (upstream JavaScriptCore has dropped 32-bit support).

We will soon be offering arm64 support as well.

Linking on Windows / MSVC
In Visual Studio, go to Linker → General → Additional Library Directories in your project's properties and set one of the following:

 $(ULTRALIGHT_SDK_ROOT)/lib/win/x64/
Then, go to Linker → Input → Additional Dependencies and add the following:

Ultralight.lib
UltralightCore.lib
WebCore.lib
AppCore.lib
Note: AppCore.lib is optional, only link if you use the AppCore API headers..

Linking on Linux
First, copy the shared libraries in $(ULTRALIGHT_SDK_ROOT)/bin/linux to your OS's standard library directory.

Then, add the following to your Makefile's LDFLAGS:

-lUltralight -lUltralightCore -lWebCore -lAppCore
Note: -lAppCore is optional, only link if you use the AppCore API headers..

Linking on macOS
Within XCode, select your target and go to General → Linked Frameworks and Libraries and add the following:

libUltralightCore.dylib
libUltralight.dylib
libWebCore.dylib
libAppCore.dylib
Or alternatively, if you are building with a Makefile, add the following to your LDFLAGS:

-lUltralight -lUltralightCore -lWebCore -lAppCore
Note: AppCore is optional, only link if you use the AppCore API headers..
