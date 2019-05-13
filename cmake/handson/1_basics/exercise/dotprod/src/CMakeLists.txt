add_library(dotprod dotprod.cc)

include(GNUInstallDirs)
install(TARGETS dotprod DESTINATION ${CMAKE_INSTALL_LIBDIR})

install(DIRECTORY src/ DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/dotprod 
  FILES_MATCHING PATTERN "*.h*")
