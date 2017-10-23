cmake_minimum_required(VERSION 2.8)
project(example)
#设置OpenCV_DIR为包含OpenCVConfig.cmake的目录
set(OpenCV_DIR "/home/cvrsg/opencv-build/opencv-3.2.0/share/OpenCV")
find_package(OpenCV REQUIRED)
add_executable(example example.cpp)
target_link_libraries(example ${OpenCV_LIBS})
