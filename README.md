# Rotating Cube

A simple OpenGL program written in C++ to test out 3d rendering.

## Requirements

- A linux system
- Cmake ^3.31
- GLFW

## How do I run it on my system?

Clone this repo into your system and cd inside of the repo directory

```
git clone https://github.com/D0T-B0X/RotatingCube.git
cd RotatingCube
```

Run cmake to generate the build files for our project and compile it.

```
cmake -S . -B build
cmake --build build
```

Next, cd into the build directory and run the executable

```
cd build/
./RotatingCube
```

And, Voila! You now have the Rotating Cube on your screen!

<mark><code>!! If you are on a windows system, make sure cmake is installed and edit `CMakeLists.txt` to use windows path syntax !!</code></mark>

## Parameters

You can tweak certain parameters in the program to change how the cube or the camera behaves:

- SCR_WIDTH: Width of the screen
- SCR_HEIGHT: Height of the screen
- AVELOCITY: How fast you want the cube to spin
- ROTATION_ANGLE: Angle at which the cube will rotate
- SCR_DISTANCE: Distance of the cube from the screen (decreasing this makes the cube appear further)
- FOV: Field of view

`SCR_WIDTH`, and `SCR_HEIGHT` essentially control the resolution of the render.