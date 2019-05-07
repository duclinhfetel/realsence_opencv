cmake_minimum_required(VERSION 2.8)
project(realsence_opencv)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package (realsense2 REQUIRED)
find_package( OpenCV REQUIRED)

include_directories(
    ${OpenCV_INCLUDE_DIRS}
    ${realsense2_INCLUDE_DIRS}
)
link_directories(
    ${realsense2_LIBRARY_DIRS}
    ${OpenCV_LIBRARY_DIRS}
)

FILE(GLOB SRC_FILES *.cpp)

add_executable( realsence_opencv ${SRC_FILES} )
target_link_libraries(realsence_opencv realsense2::realsense2 ${OpenCV_LIBS} ${realsense2_LIBRARIES})
