# arch以及xfce安装过程一些问题的解决记录

## thunar文件管理器无法解压缩以及压缩
安装xarchiver或者选择其他的archive manager，详见 https://wiki.archlinux.org/index.php/List_of_applications/Utilities#Archive_managers

## wifi连接不稳定经常崩溃
本人目前使用的是network manager，但是在刚开始的时候经常会莫名其妙的卡死，设置的vpn也只能连接一次就失效了，之后发现是自己没有安装桌面通知的原因，当wifi想发出通知的时候变卡死了。解决办法，安装xfce4-notifyd。详见 https://wiki.archlinux.org/index.php/Desktop_notifications#Notification_servers

## thunderbird状态栏插件
由于thunderbird无法最小化到状态栏，使用birdtray便可以解决。
```bash
yay -S birdtray
```

## 右键创建新文件为空
此时执行
```bash
cat ~/.config/user-dirs.dirs
```
查看template，应当是如下样式
```bash
# This file is written by xdg-user-dirs-update
# If you want to change or add directories, just edit the line you're
# interested in. All local changes will be retained on the next run.
# Format is XDG_xxx_DIR="$HOME/yyy", where yyy is a shell-escaped
# homedir-relative path, or XDG_xxx_DIR="/yyy", where /yyy is an
# absolute path. No other format is supported.
# 
XDG_DESKTOP_DIR="$HOME/Desktop"
XDG_DOWNLOAD_DIR="$HOME/Downloads"
XDG_TEMPLATES_DIR="$HOME/Templates"
XDG_PUBLICSHARE_DIR="$HOME/Public"
XDG_DOCUMENTS_DIR="$HOME/Documents"
XDG_MUSIC_DIR="$HOME/Music"
XDG_PICTURES_DIR="$HOME/Pictures"
XDG_VIDEOS_DIR="$HOME/Videos"
```
其中的XDG_TEMPLATES_DIR便指定了模板的目录，如果不是的
```bash
"$HOME/Templates"
```
可以通过
```bash
xdg-user-dirs-update --set TEMPLATES ~/Templates
```
来设定，其中xdg-user-dir的安装以及详细用法详见 https://wiki.archlinux.org/index.php/XDG_user_directories
然后你可以向Templates的文件夹中创建一些新文件，（可能需要logout一下）之后在右键的新建文件中便可以找到你刚才创建的模板。
（我觉得应该有命令可以创建一些常用的模板，但是我并没有找到，如果你知道的话，希望通过留言告诉我，谢谢）

## 想起来或者遇到了再写。。。