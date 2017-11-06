# 编译安装tensorflow

## 获取源码

```sh
git clone --recurse-submodules https://github.com/tensorflow/tensorflow
git clone https://github.com/tensorflow/tensorflow
```

其中–recurse-submodules 参数是必须的, 用于获取 TesorFlow 依赖的 protobuf 库.

## 安装bazel

安装bazel依赖环境

```sh
# 貌似不需要
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt-get update
sudo apt-get install openjdk-8-jdk
sudo update-alternatives --config java
sudo update-alternatives --config javac
```

```sh
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

编译安装bazel：从下面的链接里下载  bazel-0.7.0-installer-linux-x86_64.sh

[bazel——link]: https://github.com/bazelbuild/bazel/releases

```sh
sudo chmod 777 bazel-0.7.0-installer-linux-x86_64.sh
./bazel-0.7.0-installer-linux-x86_64.sh --user
```

然后bazel就已经编译好了，在`/home/kyxu/.bazel/bin`文件夹下，将这个路径加入到bashrc中：

```
export PAHT=/home/kyxu/.bazel/bin:$PATH
```

就完成bazel的编译安装

## 编译tensorflow

