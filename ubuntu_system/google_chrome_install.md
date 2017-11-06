## install google-chrome

### 下载deb安装包

* 32位：

  ```sh
  wget https://dl.google.com/linux/direct/google-chrome-stable_current_i386.deb
  ```

* 64位

  ```sh
  wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
  ```

### 安装deb

```sh
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

* 如果碰到依赖未满足，则用 `sudo apt-get -f install`，然后再次安装即可

### 无法启动的问题

报错如下：

```
[0807/144244.712736:FATAL:nss_util.cc(627)] NSS_VersionCheck("3.26") failed. NSS >= 3.26 is required. Please upgrade to the latest NSS, and if you still get this error,
contact your distribution maintainer.
```

解决方法：

```sh
sudo apt install --reinstall libnss3
```

