cmake_minimum_required(VERSION 3.0)
project(Boost CXX)


# stacktrace is not included into the cmake yet
# thus we need to link boost_stacktrace_basic manually
FIND_PACKAGE(Boost COMPONENTS system REQUIRED)
INCLUDE_DIRECTORIES (${Boost_INCLUDE_DIRS})

ADD_EXECUTABLE(demo1 demo1.cpp)
TARGET_LINK_LIBRARIES(demo1 ${Boost_LIBRARIES} boost_stacktrace_basic dl)

ADD_EXECUTABLE(demo2 demo2.cpp)
TARGET_LINK_LIBRARIES(demo2 ${Boost_LIBRARIES})
