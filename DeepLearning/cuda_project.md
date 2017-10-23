# CUDA项目CMakeLists.txt编写

当项目里需要用到cuda，比如视频硬解码，则需要编写带cuda的CMakeLists.txt文件。

如下是一个CMakeLists.txt示例：

```c++
cmake_minimum_required(VERSION 2.8)

project(ffmpeg_hw_decode )  #LANGUAGES CXX CUDA

set(CMAKE_CXX_STANDARD 11)

#set(OpenCV_DIR "/home/cvrsg/Downloads/opencv-2.4.13/build_install/share/OpenCV")
#find_package(OpenCV REQUIRED)
find_package(CUDA REQUIRED)

list(APPEND CUDA_NVCC_FLAGS "-arch=sm_61;-std=c++11")

include_directories(
        ${PROJECT_SOURCE_DIR}/include
        ${PROJECT_SOURCE_DIR}/thirdParty/ffmpeg/include
        ${CUDA_INCLUDE_DIRS}
        /home/cvrsg/Downloads/opencv-2.4.13/build_install/include
)
link_directories(
        ${PROJECT_SOURCE_DIR}/thirdParty/ffmpeg/lib
        /home/cvrsg/Downloads/opencv-2.4.13/build_install/lib
)

set(ffmpeg_lib
        avcodec
        avfilter
        avutil
        avformat
        avdevice
        swscale
        swresample
        )

set(opencv_libs
        opencv_core opencv_highgui opencv_imgproc opencv_gpu opencv_contrib
        )

set(SOURCE_FILES
        src/decode.cpp
        src/encode.cpp
        ${PROJECT_SOURCE_DIR}/thirdParty/yuv2bgr.cu
        )

cuda_add_library(decode_ultity
        ${SOURCE_FILES})
target_link_libraries(decode_ultity
        ${ffmpeg_lib}
        ${opencv_libs}
        /usr/local/cuda-8.0/lib64/libcudart.so
        )


cuda_add_executable(main src/main.cpp)
target_link_libraries(main
        decode_ultity
        pthread
        glog
        )
```

* 主要是需`list(APPEND CUDA_NVCC_FLAGS "-arch=sm_61;-std=c++11")`和每个`add`前加`cuda`

