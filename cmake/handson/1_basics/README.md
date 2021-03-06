# Part 1) Compile the dotprodcl application

Write a CMakeLists.txt to compile the dotprodcl application.
- Its only dependency is boost's program_options.
- Use a cached variable to allow the user to select the floating point precision (float/double).
  Depending on the CMake variable, set the preprocessor macro "PRECISION" to 4 (float) or 8 (double).

# Part 2) Compile and install the dotprod library

Write a CMakeLists.txt to compile the dotprod library (ignore the tests folder for now).
- Add necessary commands to install the library and its headers.

# Part 3) Compile the tests

The dotprod library contains 2 test files (assume more tests will be added later).
Write a function which takes the names of the test source files and builds an executable for each test.
- Use named arguments as explained.
- Loop over the list of test files.
- Use `test_<test_source_without_.cc>` as executable name, e.g. test_orthogonal for orthogonal.cc.
- Link with the library.

# Part 4) (optional) Link dotprod with dotprodcl

Now use the dotprod library in the dotprodcl application.
- First define the macro ENABLE_LIBRARY when compiling the executable. (Don't use this patterns in your project!)
- Write the necessary commands to find header and library.
 