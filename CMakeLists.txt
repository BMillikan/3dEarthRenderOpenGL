cmake_minimum_required(VERSION 3.5.1)
message(STATUS "CMake version: ${CMAKE_VERSION}")

project( hw3 )

include_directories( ./inc )
#include(CMakePrintHelpers)
find_package( OpenGL REQUIRED )
find_package( GLUT REQUIRED )
include_directories( AFTER ${OPENGL_INCLUDE_DIRS} ${GLUT_INCLUDE_DIRS} )

link_directories( ./lib )

#add_definitions(-DHIRES)
add_compile_options(-O3)

# hw3
add_executable( hw3 hw3.cpp glinit.cpp glentry.cpp utils.cpp )

target_link_libraries( hw3 ${OPENGL_LIBRARIES} )
target_link_libraries( hw3 ${GLUT_LIBRARY} )
target_link_libraries( hw3 pthread SOIL )
