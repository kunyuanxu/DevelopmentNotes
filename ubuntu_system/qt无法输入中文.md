# 解决qt无法输入中文

1. `sudo apt-get install fcitx-frontend-qt5`
2. `sudo cp /usr/lib/x86_64-linux-gnu/qt5/plugins/platforminputcontexts/libfcitxplatforminputcontextplugin.so /opt/Qt5.7.0/5.7/gcc_64/plugins/platforminputcontexts/ `
3. `sudo cp /usr/lib/x86_64-linux-gnu/qt5/plugins/platforminputcontexts/libfcitxplatforminputcontextplugin.so /opt/Qt5.7.0/Tools/QtCreator/lib/Qt/plugins/platforminputcontexts/`
4. 重启电脑

