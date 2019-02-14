cmake_minimum_required (VERSION 2.6)
project (Tutorial)

# The version number
set (Tutorial_VERSION_MAJOR 1)
set (Tutorial_VERSION_MINOR 0)

# should we use our own math functions
option(USE_MYMATH "Use tutorial provided math implementation" ON)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file (
    "${PROJECT_SOURCE_DIR}/TutorialConfig.h.in"
    "${PROJECT_SOURCE_DIR}/TutorialConfig.h"
)

# add the binary tree to the search path for include files
# so that we will find TutorialConfig.h
include_directories("${PROJECT_BINARY_DIR}")

# add the MathFunctions library?
#
if (USE_MYMATH)
    # The source file mysqrt.cpp has one function called mysqrt 
    # that provides similar functionality to the compiler’s sqrt function. 
    # To make use of the new library we add an add_subdirectory call in 
    # the top level CMakeLists.txt file so that the library will get built.
    # We also add another include directory so that the MathFunctions/MathFunctions.h 
    # header file can be found for the function prototype.
    include_directories("${PROJECT_SOURCE_DIR}/MathFunctions")
    add_subdirectory(MathFunctions)
endif (USE_MYMATH)

# add the executable
add_executable(Tutorial tutorial.cpp)
target_link_libraries(Tutorial MathFunctions)