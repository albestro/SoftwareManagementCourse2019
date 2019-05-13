cmake_minimum_required(VERSION 3.14)

project(dotprodcl LANGUAGES CXX)

find_package(Boost REQUIRED COMPONENTS program_options)

add_subdirectory(src)
