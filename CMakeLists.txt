cmake_minimum_required(VERSION 3.5)

project(OpenCV_Tutorial)

#set(OpenCV_DIR /media/jack/data/ubuntu/OpenCV/401usr/local/lib/cmake/opencv4)

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -march=native")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unknown-pragmas -Wfatal-errors -fPIC -O3 -fstrict-aliasing -fprefetch-loop-arrays -fexceptions")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Dlinux -fsigned-char -ftree-vectorize -DOMP_NUM_THREADS=8 -frtti -fopenmp -fvisibility=hidden -ffast-math")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fvisibility-inlines-hidden -fomit-frame-pointer -fstrict-aliasing -ffunction-sections -fdata-sections")

add_executable(${PROJECT_NAME} dnn_tutorial/dnn_yolov3.cpp)

target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})
