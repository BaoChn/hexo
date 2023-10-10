---
title: 🧼 镜头画面污点修复（LR篇）
date: 2023-09-08 17:58:40
tags: [Lightroom,视频处理]
categories: Skill
description: 解决粗心摄像师的一大困扰
cover: https://a-b.cc/wp-content/uploads/0d26071c-b267-43fc-94df-8055a05412d7.webp
---
{% note info flat %}这里采用的思路是 ①视频转序列图 ②Lr 批量修复 ③合成输出视频 来实现镜头去污，下面详细展开说明：{% endnote %}
### 0. 准备工作
将使用到 [Adobe Lightroom Classic, Media Encoder 与 After Effects](https://fxhub.cn/adobe)，可前往独家素材站获取带有[Lr]和[Me]前缀的安装包👇
{% link Adobe｜素材宝库,fxhub.cn,https://fxhub.cn/adobe %}

### 1. 首先将要处理的视频转化为序列图（使用 Media Encoder）
- 将视频导入 文件 > 添加源
  {% image https://a-b.cc/wp-content/uploads/Remove-Stain-Step-1.webp, alt=也可直接拖拽视频到队列 %}
- 修改格式为 PNG 并设置导出位置（需单独自建文件夹）
  {% image https://a-b.cc/wp-content/uploads/Remove-Stain-Step-1.webp, alt=导出格式也可设置为 JPEG %}
- 确认无误后点击 绿三角 启动转换

### 2. 启动 Lightroom Classic 导入序列图：
- 顶部菜单 `文件` > `导入照片和视频` 进入图库板块
  {% image https://a-b.cc/wp-content/uploads/Remove-Stain-Step-0.webp %}
- `选择源` > `其他源` 找到序列图所在文件夹后点击右下角的 导入 按钮

### 3. 进行单张污点修复
- 进入界面右上角 `修改图片` 板块，在右侧面板中找到修复 🩹 图标（快捷键 {% kbd Q %} ），涂抹画面中需要修复的部位
  {% image https://a-b.cc/wp-content/uploads/Remove-Stain-Step-3.webp %}

### 4. 批量化处理 
- 首先在底部图片列表，务必选中第二张图片
- 按下键盘 {% kbd Ctrl %} + {% kbd A %} 全选图片，将鼠标悬停在第二张图片上
  {% image https://a-b.cc/wp-content/uploads/Remove-Stain-Step-4.webp %}
- 鼠标右键 `菜单` > `修改图片设置` > `粘贴前面的设置` 进行修复（需等待片刻完成处理）

### 5. 菜单栏 `文件` > `导出` 将已修复的序列图重新导出

### 6. 最后使用 AE 合成为视频（也可使用 PR/Blender/FFmpeg）
- 顶部菜单 `文件` > `导入` > `文件` 打开导入窗口
- 选中刚才导出的序列图，勾选 `PNG序列` 和 `创建合成` 进行导入
- 按需要将原音频拖入轨道
- 输出合成为视频即可~
  {% image https://a-b.cc/wp-content/uploads/image-2.webp %}
