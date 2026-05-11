---
title: "Sulphur 2 “无审查”开源 AI 视频模型本地部署简报 脑图"
type: mindmap
source: raw/notebooklm-mindmaps/Sulphur-2-无审查-开源-AI-视频模型本地部署简报.json
---

```mindmap
root((｛'name': 'Sulphur 2 无审查 AI 视频模型', 'children': 【｛'name': '模型特))
  ｛'name': '模型特点', 'children': 【｛'name': '完全免费开源'｝, ｛'name': '
    ｛'name': '完全免费开源'｝
    ｛'name': '100% 无审查'｝
    ｛'name': '支持本地部署'｝
    ｛'name': '硬件需求低 （8G显存）'｝
    ｛'name': '支持文生视频'｝
    ｛'name': '支持图生视频'｝
  ｛'name': '环境准备', 'children': 【｛'name': '下载最新版 CF 客户端'｝, ｛'na
    ｛'name': '下载最新版 CF 客户端'｝
    ｛'name': '安装并运行客户端'｝
    ｛'name': '配置硬件 （N卡/A卡/CPU）'｝
    ｛'name': '设置自动更新与文件目录'｝
  ｛'name': '模型下载与配置', 'children': 【｛'name': '主模型 （Checkpoints）
    ｛'name': '主模型 （Checkpoints）', 'children': 【｛'name': 'BF16 精度
      ｛'name': 'BF16 精度 （46G, 高配）'｝
      ｛'name': 'FP8 精度 （27G, 8G显存推荐）'｝
      ｛'name': '量化版 （极低配置）'｝
    ｛'name': '附加组件', 'children': 【｛'name': '加速器 （需大显存）'｝, ｛'name
      ｛'name': '加速器 （需大显存）'｝
      ｛'name': 'GGUF 文本提词量化器'｝
    ｛'name': '文件存放', 'children': 【｛'name': '主模型放入 Models/checkpo
      ｛'name': '主模型放入 Models/checkpoints'｝
      ｛'name': '提词器放入 Models/GGUF'｝
  ｛'name': '使用步骤', 'children': 【｛'name': '加载 LTX2.3 模板'｝, ｛'na
    ｛'name': '加载 LTX2.3 模板'｝
    ｛'name': '上传底图 （图生视频）'｝
    ｛'name': '切换主模型为无审查模型'｝
    ｛'name': '编写提示词 （Prompt）'｝
    ｛'name': '调整分辨率与时长'｝
    ｛'name': '点击运行生成'｝
  ｛'name': '输出与管理', 'children': 【｛'name': '自动配置音效'｝, ｛'name': 
    ｛'name': '自动配置音效'｝
    ｛'name': '视频存放于 output/V 文件夹'｝
    ｛'name': '支持拖入工作流文件'｝
```
