cmake_minimum_required(VERSION 3.0)
project(Boost CXX)

FIND_PACKAGE(Boost COMPONENTS context REQUIRED)
INCLUDE_DIRECTORIES (${Boost_INCLUDE_DIRS})

EXECUTE_PROCESS( COMMAND uname -m COMMAND tr -d '\n' OUTPUT_VARIABLE ARCHITECTURE )

# demo1.cpp uses Intel-specific SIMD instructions, so it is disabled
# on other architectures
if( ${ARCHITECTURE} STREQUAL "x86_64" )
  ADD_EXECUTABLE(demo1 demo1.cpp)
  TARGET_LINK_LIBRARIES(demo1 ${Boost_LIBRARIES})
endif()

ADD_EXECUTABLE(demo2 demo2.cpp)
TARGET_LINK_LIBRARIES(demo2 ${Boost_LIBRARIES})
