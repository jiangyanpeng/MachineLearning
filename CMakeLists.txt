cmake_minimum_required(VERSION 3.15)
project(MachineLearning)
######
set( CMAKE_CXX_COMPILER "g++" )
set( CMAKE_BUILD_TYPE "Release" )
set( CMAKE_CXX_FLAGS "-std=c++11 -march=native -O3" )
set(CMAKE_CXX_STANDARD 11)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
###include head
include_directories(${PROJECT_SOURCE_DIR}/include)

####### DEPENDENCIES #######
#find_package(OpenCV 3 REQUIRED)
###include dependencies head

###shared lib
add_library(ML SHARED  src/test.cpp)
###executable
add_executable(MachineLearning main.cpp )
###link local lib and ${OpenCV_LIBS}
target_link_libraries(MachineLearning ${ML})