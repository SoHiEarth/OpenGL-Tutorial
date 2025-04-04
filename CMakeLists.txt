cmake_minimum_required(VERSION 3.10)
project(LearningOpenGL VERSION 1.0)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True) 

file(GLOB_RECURSE SOURCES src/*.cc src/*.c)
file(GLOB_RECURSE HEADERS src/*.h)

add_subdirectory(external/glfw)
find_package(OpenGL REQUIRED)

add_executable(LearningOpenGL ${SOURCES} ${HEADERS})
target_include_directories(LearningOpenGL PRIVATE include)
target_link_libraries(LearningOpenGL PRIVATE ${OPENGL_LIBRARIES})
target_link_libraries(LearningOpenGL PRIVATE glfw)
