# C++ Orbital Mechanics & Solar System Simulator

A real-time C++ application for simulating and visualising orbital mechanics using Newtonian gravity. The project combines numerical physics simulation with a custom OpenGL rendering pipeline and an ImGui-based user interface for real-time interaction.

Rather than relying on closed-form orbital solutions, trajectories emerge dynamically from force calculations and numerical integration, allowing flexible experimentation with multi-body systems.

---

## Overview

This simulator models celestial bodies as interacting point masses governed by Newton’s Law of Universal Gravitation. At each timestep, gravitational forces are accumulated, accelerations are computed, and the system state is advanced numerically. The resulting motion is rendered in real time using OpenGL.

The project was designed to explore how classical mechanics translates into stable, maintainable simulation code while keeping a clear separation between physics, rendering, and application logic.

---

## Key Features

- N-body gravitational simulation using Newtonian gravity  
- Time-stepped numerical integration of equations of motion  
- Real-time OpenGL visualisation of bodies and orbital trajectories  
- Custom C++ abstractions over OpenGL (VAO, VBO, IBO, shaders, textures)  
- Interactive Dear ImGui interface for runtime control and inspection  
- Modular architecture enabling straightforward extension  

---

## Physics Model

Bodies are modelled as point masses interacting via Newton’s Law of Universal Gravitation. Pairwise gravitational forces are computed and accumulated per timestep, after which accelerations, velocities, and positions are updated numerically. Orbital behaviour arises naturally from initial conditions rather than being analytically prescribed.

The emphasis is on physical clarity and correctness rather than visual shortcuts.

---

## Numerical Integration

The system is advanced using explicit time-stepping integration. The timestep is chosen to balance numerical stability and performance, and the code structure allows alternative integration schemes (such as symplectic methods) to be introduced cleanly in future iterations.

---

## Rendering Architecture

Rendering is handled through a lightweight OpenGL abstraction layer, including a central renderer and strongly typed wrappers around OpenGL buffer objects (VAO, VBO, IBO). Shader compilation, uniform management, and texture handling are encapsulated in dedicated classes, keeping rendering concerns isolated from simulation logic.

---

## User Interface

Dear ImGui provides a lightweight, immediate-mode interface for real-time adjustment of simulation parameters, interactive control of the simulation loop, and debug-style inspection of system state. UI layout state is generated at runtime and is not part of the simulation logic.

---

## Project Structure

Src/  
- main.cpp  
- main.h  
- Renderer.h  
- VAO.h  
- VBO.h  
- IBO.h  
- Shaders.h  
- Textures.h  

Res/  
- shaders/  
- textures/  

imgui/  
- Dear ImGui source  

CMakeLists.txt

---

## Build Instructions

Requirements:
- C++17-compatible compiler  
- OpenGL  
- CMake  
- GLFW / GLEW (or equivalent OpenGL loader)  

Build steps:

mkdir build  
cd build  
cmake ..  
make  

---

## Motivation

This project was developed to move beyond analytical mechanics and focus on numerical modelling, system design, and performance-oriented C++ development. It emphasises building a complete physics-to-visualisation pipeline rather than isolated demonstrations.

---

## Future Improvements

- Symplectic or adaptive integration schemes  
- Energy and angular momentum conservation diagnostics  
- Ephemeris-based initial conditions for real-world validation  
- Multi-threaded force evaluation  
- Extended visual analytics and plotting  

---

## Author

Rayan Fahad  
Physics undergraduate with interests in computational physics, numerical simulation, and performance-focused C++ development.
