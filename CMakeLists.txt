cmake_minimum_required(VERSION 3.11)
project(opencv-checkout)

include(FetchContent)
FetchContent_Declare(
    opencv
    URL https://github.com/opencv/opencv/archive/4.0.1.zip
)
FetchContent_GetProperties(opencv)
if(NOT opencv_POPULATED)
  FetchContent_Populate(opencv)
  add_subdirectory(${opencv_SOURCE_DIR} ${opencv_BINARY_DIR})
endif()