* 当`opencv`是使用了`cuda`编译的，在使用是会出现`cannot find -lopencv_dep_cudart`的问题，为此，在`cmakelists`中添加以下语句即可：

  ```c++
  set(CUDA_USE_STATIC_CUDA_RUNTIME OFF)
  ```

  ​

