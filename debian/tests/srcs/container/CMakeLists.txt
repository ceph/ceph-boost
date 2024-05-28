cmake_minimum_required(VERSION 3.0)
project(Boost CXX)

FIND_PACKAGE(Boost COMPONENTS container system REQUIRED)
INCLUDE_DIRECTORIES (${Boost_INCLUDE_DIRS})

ADD_EXECUTABLE(demo1 demo1.cpp)

ADD_EXECUTABLE(demo2 demo2.cpp)

ADD_EXECUTABLE(demo3 demo3.cpp)
