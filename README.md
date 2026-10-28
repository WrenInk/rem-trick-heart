# Rem Trick Heart

## 技术路线

使用图像生成工具绘制雷姆关键姿态和透明人物图层，再用 Python / OpenCV 的 SIFT 特征匹配与 RANSAC 仿射配准对齐原片镜头。按背景、人物、道具、遮挡和字幕分层合成，对指定帧段替换修订补片，最后由 FFmpeg 编码为 1280 × 720、24 fps 的 H.264 视频，并原样复制原片 AAC 音轨。

## 仓库结构

```text
assets/                  最终成片采用的图片和分层素材
  initial/               初期制作中最终沿用的图片
  rebuild/               按镜头重制后最终沿用的图片
  revision3/             第三次修订采用的图片
prompts/                 与 assets 下图片同路径、同名的提示词文本
  index.json             图片用途、提示词关联依据及来源索引
videos/
  source/trick-heart-official.mp4   原视频
  final/rem-trick-heart.mp4        最终成品视频
```

提示词保留已保存的原文；经过配准、裁剪或分层的图片注明派生关系，程序提取的图层注明处理方式。没有留存或无法确认的提示词明确标注。
