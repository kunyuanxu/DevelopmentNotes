# protobuf使用

## 安装

1. `github`上下载源码：https://github.com/google/protobuf

2. cd 到目录下

3. 安装依赖：

   ```sh
   sudo apt-get install autoconf automake libtool curl make g++ unzip
   ```

4. ```sh
   ./autogen.sh
   ```

5. 安装

   ```sh
   ./configure --prefix='安装路径'
   make -j
   make check -j
   make install
   ```

## 编译使用

* 编译proto文件

  ```sh
  /home/kyxu/kyxu/Deep_Learning/depend_softs/protobuf/build_install/bin/protoc --cpp_out=../ protoFaceEncode.proto
  ```

* 将其作为第三方库使用

  ```C++
  include_directories(${PROJECT_SOURCE_DIR}/thirdParty/include/protobuf)
  link_directories(${PROJECT_SOURCE_DIR}/thirdParty/lib/protobuf)
  target_link_libraries(deep_face_process libprotobuf.so)
  ```

