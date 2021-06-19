---
title: 系统美化
prev: /rookie/transparent.md
---

# archlinux 系统美化

> ### 🌺 爱美之心，人皆有之
>
> 这一小节将会介绍如何对 KDE 桌面环境进行美化

> ### 🔖 这一节将会讨论：
>
> [[toc]]

美化这个话题是永恒的。有些人用 Linux 的原因就是一开始被美化后桌面的截图惊艳到了。

本节介绍的步骤建议按顺序进行，您可以选择在任何一步收手，因为剩下的步骤可能显得多余，甚至可能适得其反。同时，本小节将介绍两种桌面布局方式 —— 一种是传统的类似 windows 的菜单栏布局，另一种是类似 macOS 的 Dock 栏布局。

## 0. 换一张漂亮的壁纸

1. 在桌面右键，选择`配置桌面`

2. 在新出现的窗口中右下角选择 `添加图片` 即可选择你想要的图片

## 系统图标

如果主题中的图标不能满足你，那么可以选择一些自定义的图标。_系统设置_ > _外观_ > _图标_ > _获取新图标主题_ ，搜索图标名 Tela-icon-theme，进行安装设置即可。

## 混成器

_系统设置_ > _显示和监控_ > _混成器_ 开启混成器

## SDDM 主题

你应该注意得到，输入密码时默认的登录界面是很丑的，这里也可以替换掉。_系统设置_ > _开机和关机_ > _登录屏幕(SDDM)_ > _获取新登录屏幕_ ，搜索 SDDM 主题 layan 并设置即可

## 欢迎屏幕(splashscreen)

可以对在登录界面后的欢迎屏幕进行美化。 _系统设置_ > _外观_ > _欢迎屏幕_ > _获取新欢迎屏幕_ ，搜索 miku 进行设置即可。这个`Snowy Night Miku`是群主搜索到的最好看的二刺猿属性的初始界面了，强烈建议安装。另外，还有一个大佬做了一些二次元主题的欢迎屏幕，但是质量一般，这里是他的[主页](https://www.pling.com/u/thevladsoft/)。

## 系统主题

使用一个高质量的系统主题可以直线提升系统的美观程度。_系统设置_ > _全局主题_ > _获取新的全局主题_ ，搜索主题 layan，进行设置即可。 顺便说一句，这个主题的作者 vinceliuice 是一位中国大佬，是一位设计师，他设计的主题以及图标的质量都很高，同学们可以去他的[主页](https://www.pling.com/u/vinceliuice/)为他打分和点赞。

> 如果切换主题后，windows 键不能呼出菜单，可在左下角右键，配置程序启动器，在键盘快捷键中重新设置`windows+F1`键，windows 键会显示为 Meta 键。

## 窗口装饰

在 _系统设置_ > _外观_ > _窗口装饰_ 中，获取新窗口装饰，搜索 layan，并应用即可。

## 桌面插件

在任务栏空白处右键，选择编辑面板，添加部件。

- Netspeed widget 网速组件，这个很实用
- simple monitor 系统信息
- resources monitor cpu 内存任务栏组件
- todolist 任务组件

然后把你经常使用的软件固定在任务栏即可，和群主一样的配置即可完成。

## 终端样式设置

打开 konsole， _设置_ > _编辑当前方案_ > _外观_，选择`Red-Black` 应用确认即可。

## Kvantum Manager

主题配合 Kvantum Manager 可以达到更好的效果。

```bash
sudo pacman -S kvantum-qt5
```

在[这里](https://www.pling.com/p/1325246/)下载 Layan 的 Kvantum 主题，并解压。打开 Kvantum Manager,选择主题并安装，接下来在`Change/Delete Theme`中选择 Layan,Use this theme。最后在系统设置，外观中的应用程序风格中选择 kvantum 即可。

> 如果透明的效果没有显示，确保 KDE 的全局缩放比例为整数倍。或者尝试切换混成器中 openGL 的设置。

## GRUB 主题

开机时有个漂亮的 GRUB 也是很舒服的。

在[这里](https://www.pling.com/p/1482847/)下载 Distro 的 GRUB 主题并解压。接下来 `cd` 进解压出来的文件夹，打开 konsole 输入

```bash
sudo cp . /usr/share/grub/themes/Distro -rf
```

以将主题放置在系统的 GRUB 默认文件夹内。

接着编辑 `/etc/default/grub` 文件，找到 `#GRUB_THEME=` 一行，将前面的注释去掉，并指向主题的 `theme.txt` 文件。即

```bash
#GRUB_THEME=
GRUB_THEME="/usr/share/grub/themes/Distro/theme.txt" #修改后
```

然后再在终端输入

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

更新 GRUB 即可。