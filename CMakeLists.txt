cmake_minimum_required(VERSION 3.0)
project(LIDARLite_RaspberryPi_Library VERSION 0.1.0)

include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}/include/
)

set(LIDARLITE_V3_HEADER
        ${CMAKE_CURRENT_SOURCE_DIR}/src/lidarlite_v3.cpp
)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin/lib/shared)

add_library(lidarlite_v3 SHARED ${LIDARLITE_V3_HEADER})

#Examples
set(EXAMPLES_DIR ${CMAKE_CURRENT_SOURCE_DIR}/examples)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

add_executable(llv3 ${EXAMPLES_DIR}/llv3.cpp)
target_link_libraries(llv3 lidarlite_v3)
