# Terrain-Generator

Welcome to my Procedural Terrain Generator project!

This project is a terrain generation tool that uses procedural algorithms to create realistic and customizable terrains. The generator uses Perlin noise and fractal algorithms to generate height maps, which are then used to create terrain meshes. The tool also includes a simple GUI that allows users to adjust various parameters, such as terrain size, complexity, and texture.

The code is written in C++, read the instructions on how to use it.


## How to Build the Project
To build from source the following are required:

 - C++ compiler
 - CMake 3.2+

Clone repository:
```
git clone https://github.com/kratos2377/Terrain-Generator.git

```

Pull the submodules:
```
cd Terrain-Generator
git submodule update --init --recursive
```

Make a build folder and run cmake:
Finally, create a build folder and run cmake (with whatever compiler you want as long as it supports C++17):

```
mkdir build
cd build
cmake .. -DCMAKE_CXX_COMPILER=g++-9 -DCMAKE_C_COMPILER=gcc-9
```

If you get cmake path error. Then you will have to provide g++ and gcc path. Use following commands.

## Result
You can find result in build/src folder.


The final result will look like this:
![procedural-terrain-generation example](https://github.com/kratos2377/Terrain-Generator/blob/main/results/image_1.jpeg)

https://user-images.githubusercontent.com/33194613/223132573-a69180b8-c9b8-46ec-8626-abf6203d6f73.mp4
