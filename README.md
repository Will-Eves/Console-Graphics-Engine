# CG Engine

**CG Engine** is a **3D Rendering Engine** build for **C++** projects.

To include the engine in your project:

1. Download the **engine.h** file from the **src/** directory.
2. Move the **engine.h** file into your project directory.
3. Include the **engine.h** file in your **main.cpp** file like this:

```cpp
#include "engine.h"
```

## Quick Nav

[Quick Start](#quick-start)

[Using Buffers](#using-buffers)

[Using a Camera](#using-a-camera)

[Creating Meshes](#creating-meshes)

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

## Using Buffers

Buffers are central to the engine. There are two types of buffers:

1. Render Buffers
2. Depth Buffers

Render buffers are created like this:

```cpp
CG::RenderBuffer renderBuffer = CG::createBuffer(
  200, // buffer width
  200  // buffer height
);
```

And depth buffers are created in a similar way:

```cpp
CG::DepthBuffer depthBuffer = CG::createDepthBuffer(
  200, // buffer width
  200  // buffer height
);
```

Buffers are cleared using the `CG::clear()` function, like so:

```cpp
CG::clear(
  renderBuffer,            // the buffer to be cleared
  CG::Color(255, 255, 255) // the color to clear the buffer to
);

CG::clear(
  depthBuffer,             // the buffer to be cleared
);
```

Finally, the render buffer is drawn to the screen like so:

```cpp
CG::render(
  renderBuffer // the buffer to be drawn
);
```

## Using a Camera

The camera provides the actual rendering functionality. It bridges to gap between MeshRenderers and Buffers.

A camera is created like so:

```cpp
CG::Camera camera = CG::Camera(
  renderBuffer, // the buffer that will be drawn to
  depthBuffer   // the depth buffer to check and write to
);
```

A camera has both a `camera.position` and a `camera.rotation`. These are both `CG::Vector3` instances, and can be changed to move the camera around.

## Creating Meshes
