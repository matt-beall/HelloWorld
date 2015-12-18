This repo is a very simple X-Plane plugin meant to investigate implementing OpenGL in an X-Plane plugin that is cross compiled in Linux for Windows. A problem exists when including opengl headers. I would assume it has something to do with the way I've structured the CMakeLists.txt. If someone can identify what I've done wrong, I'd appreciate the help! Thanks!

As a prerequisite, I'm using mingw...install these packages:
sudo apt-get install gcc-mingw-w64-x86-64 binutils-mingw-w64-x86-64

To compile:
From master....

   mkdir build
   cmake ..
   make


To reproduce problem, uncomment all the includes in HelloWorld.cpp and make again. I am seeing this error:

HelloWorld.cpp:22:21: fatal error: GL/glew.h: No such file or directory
 #include <GL/glew.h>




