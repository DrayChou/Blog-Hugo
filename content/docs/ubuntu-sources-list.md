---
date: 2013-04-15
layout:  post
title:  "ubuntu sources list"
tagline:
categories:
- linux
tags:
- sources
---

当前我的 ubuntu 源列表

    # deb cdrom:[Ubuntu 12.10 _Quantal Quetzal_ - Release amd64 (20121017.5)]/ quantal main restricted
    deb http://archive.ubuntu.com/ubuntu/ quantal main restricted
    deb http://security.ubuntu.com/ubuntu/ quantal-security main restricted
    deb http://archive.ubuntu.com/ubuntu/ quantal-updates main restricted

    # See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to
    # newer versions of the distribution.
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal main restricted
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal main restricted

    ## Major bug fix updates produced after the final release of the
    ## distribution.
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal-updates main restricted
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal-updates main restricted

    ## N.B. software from this repository is ENTIRELY UNSUPPORTED by the Ubuntu
    ## team. Also, please note that software in universe WILL NOT receive any
    ## review or updates from the Ubuntu security team.
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal universe
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal universe
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal-updates universe
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal-updates universe

    ## N.B. software from this repository is ENTIRELY UNSUPPORTED by the Ubuntu
    ## team, and may not be under a free licence. Please satisfy yourself as to
    ## your rights to use the software. Also, please note that software in
    ## multiverse WILL NOT receive any review or updates from the Ubuntu
    ## security team.
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal multiverse
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal multiverse
    deb http://cn.archive.ubuntu.com/ubuntu/ quantal-updates multiverse
    deb-src http://cn.archive.ubuntu.com/ubuntu/ quantal-updates multiverse

    ## N.B. software from this repository may not have been tested as
    ## extensively as that contained in the main release, although it includes
    ## newer versions of some applications which may provide useful features.
    ## Also, please note that software in backports WILL NOT receive any review
    ## or updates from the Ubuntu security team.

    # deb http://security.ubuntu.com/ubuntu quantal-security main restricted
    # deb-src http://security.ubuntu.com/ubuntu quantal-security main restricted
    deb http://security.ubuntu.com/ubuntu quantal-security universe
    deb-src http://security.ubuntu.com/ubuntu quantal-security universe
    deb http://security.ubuntu.com/ubuntu quantal-security multiverse
    deb-src http://security.ubuntu.com/ubuntu quantal-security multiverse

    ## Uncomment the following two lines to add software from Canonical's
    ## 'partner' repository.
    ## This software is not part of Ubuntu, but is offered by Canonical and the
    ## respective vendors as a service to Ubuntu users.
    # deb http://archive.canonical.com/ubuntu quantal partner
    # deb-src http://archive.canonical.com/ubuntu quantal partner

    ## This software is not part of Ubuntu, but is offered by third-party
    ## developers who want to ship their latest software.
    deb http://extras.ubuntu.com/ubuntu quantal main
    deb-src http://extras.ubuntu.com/ubuntu quantal main


    #网易163更新服务器（广东广州电信/联通千兆双线接入），包含其他开源镜像：
    deb http://mirrors.163.com/ubuntu/ quantal main restricted universe multiverse
    deb http://mirrors.163.com/ubuntu/ quantal-security main restricted universe multiverse
    deb http://mirrors.163.com/ubuntu/ quantal-updates main restricted universe multiverse
    deb http://mirrors.163.com/ubuntu/ quantal-proposed main restricted universe multiverse
    deb http://mirrors.163.com/ubuntu/ quantal-backports main restricted universe multiverse
    deb-src http://mirrors.163.com/ubuntu/ quantal main restricted universe multiverse
    deb-src http://mirrors.163.com/ubuntu/ quantal-security main restricted universe multiverse
    deb-src http://mirrors.163.com/ubuntu/ quantal-updates main restricted universe multiverse
    deb-src http://mirrors.163.com/ubuntu/ quantal-proposed main restricted universe multiverse
    deb-src http://mirrors.163.com/ubuntu/ quantal-backports main restricted universe multiverse


    #搜狐更新服务器（山东联通千兆接入，官方中国大陆地区镜像跳转至此） ，包含其他开源镜像：
    deb http://mirrors.sohu.com/ubuntu/ quantal main restricted universe multiverse
    deb http://mirrors.sohu.com/ubuntu/ quantal-security main restricted universe multiverse
    deb http://mirrors.sohu.com/ubuntu/ quantal-updates main restricted universe multiverse
    deb http://mirrors.sohu.com/ubuntu/ quantal-proposed main restricted universe multiverse
    deb http://mirrors.sohu.com/ubuntu/ quantal-backports main restricted universe multiverse
    deb-src http://mirrors.sohu.com/ubuntu/ quantal main restricted universe multiverse
    deb-src http://mirrors.sohu.com/ubuntu/ quantal-security main restricted universe multiverse
    deb-src http://mirrors.sohu.com/ubuntu/ quantal-updates main restricted universe multiverse
    deb-src http://mirrors.sohu.com/ubuntu/ quantal-proposed main restricted universe multiverse
    deb-src http://mirrors.sohu.com/ubuntu/ quantal-backports main restricted universe multiverse

备注
