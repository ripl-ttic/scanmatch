cmake_minimum_required(VERSION 2.6.0)

include(cmake/pods.cmake)

set(CMAKE_CXX_FLAGS "-std=c++11")

# automatically build LCM types.  This also defines a number of CMake
# variables, see cmake/lcmtypes.cmake for details
include(cmake/lcmtypes.cmake)
lcmtypes_build()

find_package(PkgConfig REQUIRED)
pkg_check_modules(OPENCV REQUIRED opencv)

include(cmake/ipp.cmake)

add_subdirectory(src/scanmatch)
add_subdirectory(src/scan-matcher)
