set(FP_PRECISION "float" CACHE STRING "select floating point precision")
set_property(CACHE FP_PRECISION PROPERTY STRINGS float double)

add_executable(dotprodcl dotprodcl.cc)

if(FP_PRECISION STREQUAL "float")
  target_compile_definitions(dotprodcl PRIVATE "PRECISION=4")
elseif(FP_PRECISION STREQUAL "double")
  target_compile_definitions(dotprodcl PRIVATE "PRECISION=8")
endif()

target_link_libraries(dotprodcl Boost::program_options)
