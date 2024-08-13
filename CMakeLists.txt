cmake_minimum_required(VERSION 3.10)

# Specify the vcpkg toolchain file
set(CMAKE_TOOLCHAIN_FILE "${CMAKE_SOURCE_DIR}/vcpkg/scripts/buildsystems/vcpkg.cmake")

# Set the project name
project(MyProject)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)

# Specify the vcpkg toolchain file
cmake_minimum_required(VERSION 3.10)

# Add the executable
add_executable(MyProject main.cpp)

# Find and link the GLM library
find_package(glm CONFIG REQUIRED)
target_link_libraries(MyProject PRIVATE glm::glm-header-only)

# Find and link the SDL2 library
find_package(SDL2 CONFIG REQUIRED)
target_link_libraries(MyProject PRIVATE SDL2::SDL2 SDL2::SDL2main)

find_package(OpenGL REQUIRED)
target_link_libraries(MyProject PRIVATE OpenGL::GL)

# Find and link glad
find_package(glad CONFIG REQUIRED)
target_link_libraries(MyProject PRIVATE glad::glad)