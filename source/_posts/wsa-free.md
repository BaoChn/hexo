---
title: 💡拒升 WIN11 却馋 WSA？安排！
date: 2023-03-01 11:18:00
tags: Windows 10
categories: Skill
description: 玩转 Win10 安卓应用新姿势
cover: https://a-b.cc/wp-content/uploads/wsa-cover-1.webp
---
{% folding cyan open, 什么是 Windows Subsystem for Android? %}
随着 Windows 11 的发布，其中的 [WSA 安卓子系统](https://learn.microsoft.com/en-us/windows/android/wsa/)可谓一大亮点，可以帮助用户在 PC 上无缝地使用安卓应用。但部分老机器却不符合系统升级条件，为此，WSA Patch(https://github.com/cinit/WSAPatch) 诞生了！
{% endfolding %}

### 系统要求
建议升级至 Windows 10 22H2 19045 及以上版本（可通过 {% kbd Win %} + {% kbd R %} 快捷键调出运行窗口，输入 `winver` 来查看你的系统版本）

### 环境配置
1. 进入 `控制面板` > `程序和功能` > `启用或关闭Windows功能`
{% image https://a-b.cc/wp-content/uploads/wsa-step-1.webp, alt=也可通过开始菜单右键菜单进入“控制面板” %}
2. 在 Windows 功能窗口勾选 `虚拟机平台功能`
{% image https://a-b.cc/wp-content/uploads/wsa-step-2.webp %}
{% tip warning %}配置完成后，计算机需进行一次重启{% endtip %}

### 安装步骤
1. 下载 `安装文件` 并解压至文件夹中
{% link Win10Patch_WSA_2210.40000.7.0.zip,fxhub.cn,https://fxhub.cn/d/App%EF%BD%9C%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F/Android/WSA%E5%AE%89%E5%8D%93%E5%AD%90%E7%B3%BB%E7%BB%9F/Win10Patch_WSA_2210.40000.7.0.zip %}
2. 双击运行 `Run.bat` 耐心等待安装

### 进阶玩法
1. 若未自动弹出窗口，可在开始菜单中启动 `适用于Android的Windows子系统` 软件
2. 点击窗口左侧 `开发人员` 菜单，开启 `开发人员模式`
   {% image https://a-b.cc/wp-content/uploads/wsa-step-3.webp %}
3. 下载 [搞机助手-官网 (lsdy.top)](https://lsdy.top/gjzs) 并完成安装
4. 点击 `拓展功能` 启动 `Cmd命令行`，输入 `adb connect 127.0.0.1:58526` 回车
   {% image https://a-b.cc/wp-content/uploads/wsa-step-4.webp %}

* 接下来请自行发挥~