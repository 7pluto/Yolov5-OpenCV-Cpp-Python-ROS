cmake_minimum_required(VERSION 3.22)
project(yolo)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CUDA_COMPILER "/usr/local/cuda-11.6/bin/nvcc")
set(CUDA_TOOLKIT_ROOT_DIR "/usr/local/cuda")

set(OpenCV_DIR "/home/chenwh/opencv-4.5.3/build")

find_package(OpenCV  REQUIRED)

add_executable(yolo ./yolo-tiny.cpp)

target_include_directories(yolo PRIVATE
        ${OpenCV_INCLUDE_DIR}
        )

target_link_libraries(yolo
        ${OpenCV_LIBS}
        )
