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

## 想起来或者遇到了再写。。。