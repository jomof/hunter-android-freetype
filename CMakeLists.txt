cmake_minimum_required(VERSION 3.0.2)
include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.16.15.tar.gz"
    SHA1 "6974c2150fc0d3b09de3ad1efcbf15d360647ffa"
)
project(example_project)
hunter_add_package(freetype)
find_package(freetype 2.6.2 CONFIG REQUIRED)
add_library(example SHARED example.cpp)
target_link_libraries(example freetype::freetype)

