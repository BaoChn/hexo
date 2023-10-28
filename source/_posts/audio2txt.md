---
title: 🎙️实现本地化语音转写
date: 2023-10-22 12:01:55
tags: [STT,格式转换,大模型,字幕]
categories: Skill
cover: /img/2023/audio2text/audio2text.webp
---
{% tip bell %}剪辑工作中时常有将录制内容输出文字稿的需求，便试着借助 OpenAI 公司的 [Whisper](https://github.com/openai/whisper) 并搭载 [GGML](https://huggingface.co/ggerganov/whisper.cpp) 模型来实现本地化音频转文字与实时录制转写。相比于[讯飞听见](https://www.iflyrec.com/zhuanwenzi.html)、[网易见外](https://sight.youdao.com/)等在线 STT 平台，在提升制作效率的同时，保障数据传输的安全性☂️{% endtip %}

## 准备部分
1. 这里采用的是由 [Const-me](https://github.com/Const-me/Whisper) 提供的 Whisper 客户端
2. 首先下载并保存 `Whisper` 程序主体解压至本地
   {% link 获取WhisperDesktop.zip,fxhub.cn,https://fxhub.cn/d/App%EF%BD%9C%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F/Windows/%E7%94%9F%E6%88%90%E5%BC%8FAI/%5B%E8%AF%AD%E9%9F%B3%E8%BD%AC%E6%96%87%E6%9C%AC%5DWhisper/WhisperDesktop.zip %}
3. 下载并保存 `GGML` 模型文件
   {% link 获取ggml-medium.bin,fxhub.cn,https://fxhub.cn/d/App%EF%BD%9C%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F/Windows/%E7%94%9F%E6%88%90%E5%BC%8FAI/%5B%E8%AF%AD%E9%9F%B3%E8%BD%AC%E6%96%87%E6%9C%AC%5DWhisper/ggml-medium.bin %}
4. 运行 WhisperDesktop 目录内的 `WhisperDesktop.exe`
5. 弹出程序窗口后，点击 Model Path 右侧 {% kbd … %} 选择已保存的 `ggml-medium.bin` 文件
   ![](/img/2023/audio2text/step-1.png)
## 一、音频转文字
1. 在 Language 内选择文件内的语言（Chinese）
   ![](/img/2023/audio2text/step-2.png)
2. 分别在下面两个路径地址框后方选择需转换的文件和输出数据文件的位置
3. 在 Output Format 选择输出数据类型：
   ![](/img/2023/audio2text/step-3.png)
4. 点击 {% kbd Transcribe %} 开始转换，等候弹窗提示完成即可
   ![](/img/2023/audio2text/step-4.png)

## 二、实时录制转写
1. 点击底部 {% kbd Audio&nbsp;Capture %} 切换模式
2. 选择 Capture Device 录制设备
   ![](/img/2023/audio2text/step-5.png)
3. 勾选 Save to text file 并输出文字文件位置
4. 点击 {% kbd Capture %} 开始转换
   {% note success simple %}此时可以开始对着麦克风发言{% endnote %}
5. 弹出的窗口内将展示已转换的内容（支持多语种混淆转译）
   ![](/img/2023/audio2text/step-6.png)
6. 发言完毕后点击原窗口 {% kbd Stop %} 即可结束录制
7. 文件将保存在此前设置的位置！Enjoy~

> ### 🌟 One more thing
> 此外推荐个更易上手的 Whisper 客户端 —— [Memo](https://memo.ac/zh/)
> ![Memo界面](https://vip2.loli.io/2023/10/04/XfLIBzcvK65CxEJ.png)
> {% link 测试资格需自行申请,store.memo.ac,https://store.memo.ac/ %}