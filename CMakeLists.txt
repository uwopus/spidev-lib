cmake_minimum_required(VERSION 2.6)

project(spidev-lib)
set(CMAKE_CXX_FLAGS "-g -Wall")
set(CMAKE_C_FLAGS "-g -Wall")


add_library(spidev-lib src/spidev_lib.c)
add_library(spidev-lib++ src/spidev_lib++.cc)

target_include_directories(spidev-lib PUBLIC src/)

INSTALL(TARGETS  spidev-lib  spidev-lib++
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
)
INSTALL( FILES src/spidev_lib.h DESTINATION include)
INSTALL( FILES src/spidev_lib++.h DESTINATION include)

