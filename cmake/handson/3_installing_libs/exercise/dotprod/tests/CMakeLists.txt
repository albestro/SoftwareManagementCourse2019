include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY git@github.com:google/googletest.git
)

FetchContent_MakeAvailable(googletest)

function(create_test_executables)
    set(options)
    set(oneValueArgs)
    set(multiValueArgs SOURCES)
    cmake_parse_arguments(ARG "${options}" "${oneValueArgs}" "${multiValueArgs}" ${ARGN})

    foreach(src IN LISTS ARG_SOURCES)
        get_filename_component(filename_without_suffix ${src} NAME_WE)
        set(test_name "test_${filename_without_suffix}")
        add_executable(${test_name} ${src})
        target_link_libraries(${test_name} dotprod)

        # link with googletest library
        target_link_libraries(${test_name} gtest_main)
    endforeach()
endfunction()

include(ExternalProject)
ExternalProject_Add(googletest
    SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/../external/googletest-1.7.0
    INSTALL_COMMAND ""
    )

create_test_executables(SOURCES
    norm.cc
    orthogonal.cc)
