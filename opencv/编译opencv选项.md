## 编译OpenCV选项

```sh
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/home/OpenCV
```

```sh
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX='/home/cvrsg/Downloads/opencv-3.2.0/build_install' -D CUDA_ARCH_BIN=6.1 -D CUDA_ARCH_PTX="" -D WITH_CUDA=ON -D WITH_CUBLAS=ON -D WITH_NVCUVID=ON ..

```