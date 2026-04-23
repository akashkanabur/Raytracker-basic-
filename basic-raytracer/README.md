# 🎨 Basic C++ Raytracer

A lightweight, high-performance raytracer built from scratch in C++. This project implements the core principles of optics and computer graphics to render 3D scenes into 2D images.

---

## 🚀 How to Run

To compile and run this project, you need a C++ compiler (like `g++` or `clang`) installed on your system.

### 1. Compile the Project
Open your terminal/command prompt and navigate to the project directory:
```bash
g++ -O3 main.cpp -o raytracer.exe
```
> **Note:** The `-O3` flag enables aggressive optimizations, making the rendering process significantly faster.

### 2. Run the Executable
```bash
./raytracer.exe
```

### 3. View the Output
The program generates a file named `renderOutput.ppm`. You can open this file using:
- **Photoshop** or **GIMP**
- **IrfanView**
- A specialized PPM viewer
- Online PPM viewers

---

## 📚 C++ Basics Used in this Project

This project serves as an excellent practical application of fundamental C++ concepts:

### 1. Header Files (`.h`) & Modularization
The code is split into logical components:
- `vec.h`: Handles 3D vector mathematics.
- `color.h`: Manages RGB color representations.
- `ray.h`: Defines the ray class (origin + direction).
- `main.cpp`: The core rendering loop.

### 2. Classes and Structs
We use `class` and `struct` to encapsulate data and behavior. For example, the `vec3` class uses **Operator Overloading** to allow mathematical operations between vectors just like primitive types:
```cpp
vec3 a(1, 2, 3);
vec3 b(4, 5, 6);
vec3 c = a + b; // Enabled via operator+ overloading
```

### 3. Namespaces & Standard Library
The project utilizes the C++ Standard Library (`std`):
- `std::iostream`: For logging progress to the console.
- `std::ofstream`: For writing the image data to a file.
- `std::cmath`: For square roots and absolute values.

### 4. Loops and Iteration
The rendering engine uses nested `for` loops to iterate through every pixel of the image, calculating the color by shooting rays into the scene.

---

## 🛠️ Technical Implementation

### The Rendering Pipeline
1.  **Camera Setup**: Defines the viewport and the camera's position in space.
2.  **Ray Generation**: For every pixel $(i, j)$, a ray is projected from the camera into the 3D scene.
3.  **Intersection Testing**: The `hit_sphere` function uses the quadratic formula to check if a ray intersects with a sphere.
4.  **Color Calculation**: If a hit occurs, the color is calculated based on the surface normal; otherwise, a background gradient (sky) is rendered.
5.  **Output**: Data is written in the **PPM (Portable Pixmap)** format, which is a simple text-based image format.

---

## 📂 File Structure
- `main.cpp` - Entry point and rendering logic.
- `vec.h` - Vector operations (dot product, cross product, unit vectors).
- `ray.h` - Ray definition.
- `color.h` - Color utility functions.
- `renderOutput.ppm` - Created after running the program.

---

### 🌟 Acknowledgments
Inspired by the "Ray Tracing in One Weekend" series. Optimized for learning and performance.