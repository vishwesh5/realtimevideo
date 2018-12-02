cmake_minimum_required(VERSION 2.8)
project( RespiCPP )
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")
ADD_DEFINITIONS(
    -std=c++11
    -D EXECU
)

#find_package( OpenCV 3 REQUIRED )
SET(OpenCV_DIR /home/hp/OpenCV_installation/installation/OpenCV-3.4.3/share/OpenCV)
find_package( OpenCV 3 REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
include_directories(".")

add_executable(
  respi
  main.cpp
  respi.cpp
  realtime.cpp
  helpers.cpp
)

target_link_libraries( respi
  ${OpenCV_LIBS}
)
