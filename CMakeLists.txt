# pa1 homework1 for VSLAM course by yuzhenning
# 20200603
cmake_minimum_required(VERSION 3.5.1)
SET(CMAKE_BUILD_TYPE "Release")
PROJECT(sayhello)
# add head file
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/include)
# add programable file
ADD_EXECUTABLE(sayhello ${PROJECT_SOURCE_DIR}/useHello.cpp)
# add lib and link
ADD_LIBRARY(hello SHARED ${PROJECT_SOURCE_DIR}/src/hello.cpp)
TARGET_LINK_LIBRARIES(sayhello hello)
# install
INSTALL(TARGETS hello LIBRARY DESTINATION /usr/local/lib)
INSTALL(FILES ${PROJECT_SOURCE_DIR}/include/hello.h DESTINATION /usr/local/include)

