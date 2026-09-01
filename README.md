# 3D Terminal Renderer

This project is a **3D Rendering Engine** for **C++**.

To include the engine in your project:

1. Download the **engine.h** file from the **src/** directory.
2. Move the **engine.h** file into your project directory.
3. Include the **engine.h** file in your **main.cpp** file like this:

```cpp
#include "engine.h"
```

## Quick Nav

[Quick Start](#quick-start)

## Quick Start

The basic skeleton of a project using this engine looks like this:

```cpp
#include "engine.h"

int main(){
  CG::setup(
    200, // screen width
    200  // screen height
  );

  // clears the console to prepare for rendering
  CG::clearScreen();

  while(true){
    // rendering code goes here
  }
}
```
