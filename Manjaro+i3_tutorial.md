# 1. 装机
## 1.1 Manjaro.cn
### （1）Manjaro XFCE版 （轻量）
### （2）Manjaro KDE版
### （3）Manjaro GNOME版（推荐）
## 1.2 rufus制作启动盘
注意：Manjaro需要用DD模式来安装
## 1.3 进入BIOS
### （1）Lenovo-F1
## 1.4 设置启动方式
1. 更换U盘为启动盘;（将启动级别调到最高）
2. 保存重启;
3. 注意：安装好之后一定要记得把启动盘从U盘设置回硬盘！！！

# 2. 安装Manjaro
## 2.1 一顿下一步
## 2.2 分区方式
### （1）双系统
### （2）移除现在所有内容并分区
### （3）自定义分区
1. /
2. /home/
3. swap
4. /boot/
## 2.3 安装可能要很久，安装好之后重启，切记拔掉U盘

# 3. 设置pacman

## 3.0 pacman教学
### （1）软件安装
### （2）软件卸载
### （3）选项

## 3.1 改造全部国内镜像源
`sudo pacman-mirrors -c China`

## 3.2 设置镜像源
1. `sudo nano /etc/pacman.conf`
2. 编辑配置文件：
  ```vim
    [archlinuxcn]
    SigLevel = Never
    Include = /etc/pacman.d/archlinuxcn
  ```
3. `sudo -E nano /etc/pacman.conf` 将36行Color选项的注释去掉，这样pacman就有颜色高亮了;
4. `cd /etc/pacman.d/ && mkdir archlinuxcn`
将镜像源放置在这个文件下：
  ```vim
    Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

## 3.3 更新系统
`sudo pacman -Syyu`
时间有点久

# 4. vim安装及设置

# 5. shell设置
## 5.0 
1. `chsh -s` 更改默认shell
2. `alias l "ls -la"
3. `funcsave l`

## 5.1 bash
## 5.2 zsh
## 5.3 fish
1. `sudo pacman -S fish`
2. `which fish`
3. `chsh -s /usr/bin/fish`
4. `curl -L https://get.oh-my.fish | fish` 安装omf插件;
5. `fish_config` 自动打开浏览器更改fish样式;
6. `omf install wttr` 在终端下可以看天气的小东西;终端下直接输入`wttr`就可以启动;
7. 命令omf之后按TAB键发现有很多选项，可以配置主题等;

# 6. 终端设置
## 6.0 设置默认启动终端
1. `vim ~/.config/i3/config`
2. 第33行：
    bindsys $mod+Return exec alacritty
## 6.1 alacritty
1. `sudo pacman -S alacritty`
2. 在i3配置文件下设置默认启动终端
3. 刷新配置或重启;
4. `vim ~/.config/alacritty/alacritty.yml`,139行，Point size更改下默认字体大小;
5. `opacity: 0.7`设置终端透明度;

## 6.2 Simple Terminal

# 7. i3安装及设置
## 7.1 安装
1. `sudo pacman -S i3`
2. 全部选择安装
3. 安装成功后重启;
4. 注意：在重新登陆界面一定要点设置图表把启动桌面由XCF改成i3;
5. 进入后回车自动生成配置，并把WIN键设置为i3的Super键或者说Mod键;
## 7.2 设置分辨率
1. `touch ~/.Xresources`
2. vim进入这个文件
3. 里面编辑：Xft.dpi: 200
4. 保存退出
5. 重启;

## 7.2 使用
1. win+Enter 启用终端
2. win+c 启动浏览器
3. win+数字 多窗口切换
4. win+r 用方向键调整窗口大小
5. win+v垂直分屏
6. win+b水平分屏
7. win+d 打开dmemu搜索软件;

## 7.3 设置
1. `vim ~/config/i3/config`
2. 最后一行加`new_window 1pixel`去掉窗口周边蓝色的框;
3. `gaps inner 8` 各个窗口之间就有空隙了;
4. `exec_always variety`
5. `exec_always compton`
6. `exec_always fcitx`

# 8. 装机软件：

1. `sudo pacman -S screenkey` 捕捉你输入的所有按键内容并呈现至屏幕
2. `sudo pacman -S simplescreenrecorder` 录屏软件
3. `sudo pacman -S code` VSCode
4. `sudo pacman -S dmenu`
5. `sudo pacman -S xorg`改硬件设置，键盘键位
6. `sudo pacman -S lxappearance` 更改窗口主题
7. `sudo pacman -S feh` 更改壁纸
8. `sudo pacman -S variety` 利用feh来对壁纸进行管理的管理器（在i3设置文件设置开机启动）
9. `sudo pacman -S compto` 渲染器,达成各种渲染效果（设置开机启动）
10.`sudo pacman -S fcitx fcitx-im fcitx-configtool` 
11. `sudo pacman -S fcitx-sunpinyin`
    `vim ~/.xprofile`
    `export GTK_IM_MODULE=fcitx`
    `export QT_IM_MODULE=fcitx`
    `export XMODDIFIERS="@im=fcitx"`
    reboot
12. `sudo pacman -S chromium`
13. `sudo pacman -S kdenlive` shi pin jan ji
14. `sudo pacman -S gimp`
15. `sudo pacman -S vlc`
16. `sudo pacman -S virtualbox`
17. `sudo pacman -S deepin.com.qq.im`
18. `sudo pacman -S electronic-wechat`
19. `sudo pacman -S transmission-qt`
20. qbittorrent
21. 

# 9. ranger
## 9.1 Install
`sudo pacman -S ranger`

# 10. polybar
