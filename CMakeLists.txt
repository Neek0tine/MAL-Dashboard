cmake_minimum_required(VERSION 3.13)  # CMake version check
project(MAL_DASHBOARD)               # Create project "simple_example"
set(CMAKE_CXX_STANDARD 14)            # Enable c++14 standard

# Add main.cpp file of project root directory as source file
set(SOURCE_FILES src/curl.cpp)

include_directories(include)

# Add executable target with source files listed in SOURCE_FILES variable

add_library(curl SHARED src/curl.cpp)
target_link_libraries(curl -lpthread)
target_link_libraries(curl  libcurl.a)
target_link_libraries(curl -L"C:/Users/nicho/CLionProjects/MAL-Dashboar/lib")

add_executable(MAL_DASHBOARD ${SOURCE_FILES})
target_link_libraries(MAL_DASHBOARD curl)
