CMAKE_MINIMUM_REQUIRED(VERSION 3.0.2)


PROJECT(Hello)

SET(CMAKE_SYSTEM_NAME Windows)

SET(CMAKE_C_COMPILER x86_64-w64-mingw32-gcc)
SET(CMAKE_CXX_COMPILER x86_64-w64-mingw32-g++)

#SET(COMPILE_FLAGS "-lglut lglu32 -lopengl32 -lglew32 -lglfw")

FIND_PACKAGE(Eigen3 REQUIRED)

ADD_DEFINITIONS(
    -DAPL=0
    -DIBM=1
    -DLIN=0
)

ADD_LIBRARY(hello_plugin SHARED
    HelloWorld.cpp
)

TARGET_LINK_LIBRARIES(hello_plugin
    /home/matt/code/HelloWorld/SDK/Libraries/Win/XPLM_64.lib
)

SET_TARGET_PROPERTIES(hello_plugin
  PROPERTIES
  PREFIX ""
  SUFFIX .xpl
)

INCLUDE_DIRECTORIES(
    ${CMAKE_SOURCE_DIR}/SDK/CHeaders/XPLM
    ${CMAKE_SOURCE_DIR}/SDK/CHeaders/Widgets
    ${EIGEN3_INCLUDE_DIR}
)
