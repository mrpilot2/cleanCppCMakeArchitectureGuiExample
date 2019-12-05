# Preamble
cmake_minimum_required(VERSION 3.15)
project(cleanCppCMakeArchitectureGuiExample)
enable_testing()

# Project wide setup
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

# Global compile options
add_compile_options(
        $<$<CXX_COMPILER_ID:Clang>:-Wall>
        $<$<CXX_COMPILER_ID:GNU>:-Wall>
)

# Externally provided content
add_subdirectory(dependencies)

add_subdirectory(src)

# Things typically only needed if we are the top level project
if(CMAKE_SOURCE_DIR STREQUAL CMAKE_CURRENT_SOURCE_DIR)
    add_subdirectory(tests)
endif()