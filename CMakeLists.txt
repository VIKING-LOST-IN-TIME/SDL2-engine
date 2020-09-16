# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

project ("SDL2-engine")

cmake_policy(SET CMP0079 NEW)

list(APPEND CMAKE_PREFIX_PATH "${CMAKE_CURRENT_SOURCE_DIR}" "C:\\SDL2")

find_package(SDL2 REQUIRED)
# find_file(SDL2_INCLUDE_DIR NAME SDL.h HINTS SDL2)
# find_library(SDL2_LIBRARY NAME SDL2)
include_directories(${SDL2_INCLUDE_DIRS})

# Include sub-projects.
add_subdirectory ("SDL2-engine")

target_link_libraries(SDL2-engine ${SDL2_LIBRARIES})