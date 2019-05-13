cmake_minimum_required(VERSION 3.14)

project(dotprod LANGUAGES CXX)

add_subdirectory(src)

include(GNUInstallDirs)
install(TARGETS dotprod DESTINATION ${CMAKE_INSTALL_LIBDIR})

install(DIRECTORY src DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/dotprod 
  FILES_MATCHING PATTERN "*.h*")
