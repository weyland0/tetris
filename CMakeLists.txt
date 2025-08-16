cmake_minimum_required(VERSION 3.5)
project(tetris LANGUAGES CXX)

include(FetchContent)
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.0.1
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

file(GLOB_RECURSE SRC_FILES "src/*.cpp")

add_executable(tetris ${SRC_FILES})
target_compile_features(tetris PRIVATE cxx_std_23)
target_link_libraries(tetris PRIVATE SFML::Graphics)
