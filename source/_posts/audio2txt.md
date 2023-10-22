---
title: 🎙️实现本地化语音转写
date: 2023-10-22 12:01:55
tags: [格式转换,大模型,字幕]
categories: [Skill,AI]
cover: /img/2023/audio2text/audio2text.webp
---
{% tip bell %}剪辑工作上时常有将录制内容输出文字稿的需求，寻思着利用 OpenAI 的 [Whisper](https://github.com/openai/whisper) 平台并结合 [GGML](https://huggingface.co/ggerganov/whisper.cpp) 模型来实现本地化音频转文字与实时录制转写 {% endtip %}
## 准备部分
1. 下载并保存 `Whisper` 程序主体解压至本地
   {% link 获取WhisperDesktop.zip,fxhub.cn,https://fxhub.cn/d/App%EF%BD%9C%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F/Windows/%E7%94%9F%E6%88%90%E5%BC%8FAI/%5B%E8%AF%AD%E9%9F%B3%E8%BD%AC%E6%96%87%E6%9C%AC%5DWhisper/WhisperDesktop.zip %}
2. 下载并保存 `GGML` 模型文件
   {% link 获取ggml-medium.bin,fxhub.cn,https://fxhub.cn/d/App%EF%BD%9C%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F/Windows/%E7%94%9F%E6%88%90%E5%BC%8FAI/%5B%E8%AF%AD%E9%9F%B3%E8%BD%AC%E6%96%87%E6%9C%AC%5DWhisper/ggml-medium.bin %}
3. 运行 WhisperDesktop 目录内的 `WhisperDesktop.exe`
4. 弹出程序窗口后，点击 Model Path 右侧 {% kbd … %} 选择已保存的 `ggml-medium.bin` 文件
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