---
title: 💾FFmpeg 转码笔记
date: 2022-08-08 17:22:37
tags: [FFmpeg,转码]
categories: Skill
cover: https://W.A-B.CC/wp-content/uploads/FFmpeg.webp
---
## 一、配置系统环境变量
- 命令行工具获取
- 访问 https://ffmpeg.org/download.html 下载工具包并解压至任意位置

### 1. 打开系统属性
{% image https://a-b.cc/wp-content/uploads/step1.webp, alt=https://a-b.cc/wp-content/uploads/step1.webp %}

### 2. 进入 `环境变量` 界面
{% image https://a-b.cc/wp-content/uploads/step1-2.webp %}
- 依次由 `系统属性` > `高级` > `环境变量` 进入菜单

### 3. 导入 Path 配置
{% image https://a-b.cc/wp-content/uploads/step2.webp, alt=双击"Path"行进入添加界面 %}
- 进入“编辑环节变量”窗口，点击新建按钮并填写 `bin` 子目录路径(结尾需加／号)

## 二、FFmpeg 状态检测
### 1. 打开命令行工具
- 按下 {% kbd WINDOWS %} + {% kbd R %} 快捷键，弹出“命令”窗口
{% image https://a-b.cc/wp-content/uploads/step3.webp %}
- 输入 `cmd`，点击 `确定` 按钮

### 2. 检测当前 FFmpeg 版本信息
- 在弹出的命令行窗口内输入
> ffmpeg -version  
{% image https://a-b.cc/wp-content/uploads/step3-1.jpg %}
- 按下回车后，若为上图所示即可进行下一步~

## 三、视频转码步骤
首先进入视频文件所在目录，在地址栏内输入 `cmd` 按下回车：

### a. MKV 转 MP4
> ffmpeg -i 文件名.mkv -vcodec copy -acodec copy 文件名.mp4  

### b. FLV 转 MP4
> ffmpeg -i 文件名.flv -vcodec copy -acodec copy 文件名.mp4  

### c. RMVB 转 MP4
> ffmpeg -i 文件名.rmvb -vcodec copy -acodec copy 文件名.mp4  
* 输入上述代码并按下回车执行（“文件名”不可包含中文字符）

## X. 批量转换为MP4
> for /R %v IN (*.格式) do ( ffmpeg -i %v -vcodec copy -acodec copy "%~nv.mp4")
将 *.格式 替换为 *.mkv/flv/rmvb（可在 %~nv.mp4 前输入自定义输出路径）

> 更多支持的转换编码格式：
> h264：mp4、flv、avi、mov、wmv、m4v、f4v、3gp、ts
> mpeg4：mp4、avi、mov、wmv、m4v、3gp、ts
> h265：mp4、avi、mov、ts
> vp8：avi、wmv、ts、webm
> vp9：mp4、avi、wmv、ts、webm

{% folding 拓展 CMD 指令 %}
列出所支持的格式 FFMPEG -FORMATS
列出所支持的编码器 FFMPEG -ENCODERS
列出所支持的解码器 FFMPEG -DECODERS
列出所支持的编解码器 FFMPEG -CODECS
显示特定编码器的选项及其信息：FFMPEG -H ENCODER=编码器名称
显示特定解码器的选项及其信息：FFMPEG -H DECODER=解码器名称
{% endfolding %}

> 可视化 GUI 客户端推荐
> HandBrake: Open Source Video Transcoder
> https://medlexo.is-an.app/cn.php