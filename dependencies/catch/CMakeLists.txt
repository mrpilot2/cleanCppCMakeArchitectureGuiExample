include(FetchContent)

FetchContent_Declare(catch2
        GIT_REPOSITORY https://github.com/catchorg/Catch2
        GIT_TAG v2.11.0
)

FetchContent_GetProperties(catch2)

if (NOT catch2_POPULATED)
    FetchContent_Populate(catch2)
    add_subdirectory(${catch2_SOURCE_DIR} ${catch2_BINARY_DIR})
endif()