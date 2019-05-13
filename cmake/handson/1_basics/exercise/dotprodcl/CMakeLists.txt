cmake_minimum_required(VERSION 3.14)

project(dotprodcl LANGUAGES CXX)

set(FP_PRECISION "float" CACHE STRING "select floating point precision")
set_property(CACHE FP_PRECISION PROPERTY STRINGS float double)

find_package(Boost REQUIRED COMPONENTS program_options)

add_subdirectory(src)
