# 设置ubuntu鼠标移动速度

ubuntu有时鼠标移动过快，很不习惯，为此百度之。

* 输入 `xset m 1` , 在这里 `m`代表`mouse` , 1 可以随意更改，取值范围为 `0-10`

***

## 写个脚本，不用每次开机都设置

```sh
sudo gedit /usr/local/bin/mymouse.sh
```

* 在文本中输入： `xset m 1`

* 保存后，在终端输入

  ```sh
  sudo chmod +x /usr/local/bin/mymouse.sh
  ```

* 打开dash(搜索软件)，输入`gnome-session`，选择`start applications`

* 点击`add`

* name里面填`setMouse`，command里填写`/usr/local/bin/mymouse.sh`

* 保存即可