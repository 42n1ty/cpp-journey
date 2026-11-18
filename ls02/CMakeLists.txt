cmake_minimum_required(VERSION 3.16)
project(cpp_journey LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_library(mathlib STATIC src/math_utils.cpp)
target_include_directories(mathlib PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")
target_compile_options(mathlib PRIVATE -Wall -Wextra -Wpedantic)

add_executable(app main.cpp)
target_link_libraries(app PRIVATE mathlib)
target_compile_options(app PRIVATE -Wall -Wextra -Wpedantic)
