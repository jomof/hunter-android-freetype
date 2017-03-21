cmake_minimum_required(VERSION 3.0.2)
include("cmake/HunterGate.cmake")
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.18.24.tar.gz"
    SHA1 "3faff9c51e3820608aa38a26ef973312610297bf"
)
project(example_project)
hunter_add_package(freetype)
find_package(freetype 2.6.2 CONFIG REQUIRED)
add_library(example SHARED example.cpp)
target_link_libraries(example freetype::freetype)

