cmake_minimum_required(VERSION 3.5)
set(CMAKE_CXX_STANDARD 17)
project(OpenGLProject)

set(SOURCE_FILES src/main.cpp)
# Set th path to your GLFW directory
set(GLFW_DIR "${CMAKE_SOURCE_DIR}/Dependencies/GlFW")

find_package(OpenGL)

#add the executable
add_executable(${PROJECT_NAME} ${SOURCE_FILES})
#linke the glfw header file
include_directories(${PROJECT_NAME} "${GLFW_DIR}/include")
target_link_libraries(${PROJECT_NAME} OpenGL32)
target_link_libraries(${PROJECT_NAME} ${GLFW_DIR}/glfw3.lib)