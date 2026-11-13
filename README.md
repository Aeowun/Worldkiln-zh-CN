# Worldkiln 简体中文文档

**Worldkiln** 是一款面向 Windows 的 3D 游戏引擎与编辑器。开发者可以使用 **Cells** 搭建场景、塑造地形、导入 3D 资源、用 **AeoScript** 编写游戏逻辑，并将项目打包为独立运行的 Windows 游戏。

## 为什么制作中文文档？

> 我希望 Worldkiln 能让更多人更容易地迈出游戏开发的第一步，也能让有经验的开发者自由地创造自己的世界。一个人使用什么语言，不应该决定他是否能学习、尝试和分享自己的创意。将文档翻译成更多语言，是我朝这个目标迈出的一小步。
>
> — Zachary Joubert，Worldkiln 开发者

**English translation of my message:** I want Worldkiln to make game development more approachable for more people, from beginners taking their first steps to experienced developers creating their own worlds. The language someone speaks shouldn't determine whether they can learn, experiment, or share their ideas. Making the documentation available in more languages is one small step toward that goal.

> **重要声明：我不会说中文。** 本仓库的简体中文内容由人工智能辅助翻译，**尚未经中文母语人士全面校对**，可能存在语言或技术错误。如果你发现任何不准确、不自然或难以理解的内容，欢迎提交 **Pull Request（拉取请求）** 帮助修正。
>
> **AI translation disclaimer (English):** I do not speak Chinese. These documents were translated using AI and may contain errors. If anything is incorrect or unclear, please contribute a pull request with a correction!

**本仓库仅提供翻译后的文档，不包含 Worldkiln 引擎的独立中文版，也不代表编辑器界面已完成中文本地化。** API 名称、AeoScript 关键字、文件名和代码示例应保持原样。遇到差异时，请以英文官方文档和实际使用的版本为准。

[下载 Worldkiln](https://github.com/Aeowun/Worldkiln/releases) · [官方入门指南](https://aeowun.com/worldkiln/getting-started/) · [官方文档](https://aeowun.com/docs/) · [英文源仓库](https://github.com/Aeowun/Worldkiln)

## 阅读指南

- [快速入门](GETTING_STARTED.md)：安装、创建项目、建立场景、测试和导出。
- [功能介绍](FEATURES.md)：世界构建、资源管理、游戏逻辑与打包。
- [AeoScript 指南](AEOSCRIPT.md)：语言基础与保留原样的代码示例。
- [贡献翻译](CONTRIBUTING.md)：报告问题、改进术语并提交拉取请求。

## Worldkiln 可以做什么？

- **构建 3D 世界：** 使用 Cells 创建结构，使用地形工具塑造更大的场景，并设置材质、光照、天空及雾效。
- **导入模型与角色：** 导入 GLB 文件，将其作为 Actors 放入场景，并使用动画 Characters。
- **编写游戏逻辑：** 使用 AeoScript 控制输入、交互、物理、导航、UI、音频和摄像机。
- **直接测试：** 在编辑器的 **Play** 模式中测试玩法。
- **导出游戏：** 通过 **Build Game** 创建独立的 Windows 游戏。

**BETA** 表示功能仍处于开发阶段；具体功能以安装版本及官方文档为准。

## 获取 Worldkiln

根据英文仓库的文档，Worldkiln 支持 **Windows 10 和 Windows 11**。

1. 前往 [GitHub Releases](https://github.com/Aeowun/Worldkiln/releases)。
2. 下载最新安装程序和所需的可选资源。
3. 安装并启动 Worldkiln。
4. 在编辑器中创建项目，参考[中文快速入门](GETTING_STARTED.md)。

## Worldkiln V1 资源格式

下表翻译自[英文 README](https://github.com/Aeowun/Worldkiln/blob/master/README.md) 中的 V1 导入说明；后续版本可能发生变化。

| 资源类别 | 文件格式 | 文档所述支持情况 |
| --- | --- | --- |
| 3D 模型/角色 | `.glb` | 支持，推荐使用 |
| 3D 模型/角色 | `.fbx`、`.obj`、`.gltf`、`.blend` | V1 文档不提供直接导入；建议先转为 GLB |
| 图片/纹理 | `.png`、`.jpg`、`.jpeg` | 支持 |
| 图片/纹理 | `.webp`、`.svg` | 标准媒体导入器不支持 |
| 音频 | `.wav`、`.mp3` | 支持 |
| 音频 | `.ogg` | 在部分资源管理流程中可用 |
| 视频 | `.mp4` | 支持；播放兼容性与视频编码及目标平台有关 |
| 特效 | `.efkefc`、`.efkpkg` | 支持 Effekseer 特效文件或包 |

**GLB** 可以把几何体、材质、纹理、骨架和动画整合进同一个文件。部分复杂角色可能还需调整骨架或动画数据。文件扩展名符合要求并不代表一定能成功导入。

需要把 FBX、OBJ 或 Blender 模型转换为 GLB 时，可使用 [Blender](https://www.blender.org/)：检查模型方向、材质和动画，然后选择 **File → Export → glTF 2.0 → glTF Binary (.glb)**。

## 官方参考与支持

- [Worldkiln 用户指南](https://aeowun.com/worldkiln/dive/)
- [AeoScript 官方文档](https://aeowun.com/aeoscript/)
- [API 参考](https://aeowun.com/docs/reference/)
- [支持与反馈](https://aeowun.com/support/)

## Windows 下载（英文原版安装程序）

本仓库提供与 Worldkiln **官方发布版本内容一致**的 Windows 安装文件镜像。**编辑器界面仍为英文，并未制作中文本地化版本。**

| 版本 | 状态 | 下载 |
| --- | --- | --- |
| 1.0.0 | 正式版 | [下载 1.0.0](https://github.com/Aeowun/Worldkiln-zh-CN/releases/tag/win11-v1.0.0) |
| 1.0.1 | 正式版 | [下载 1.0.1](https://github.com/Aeowun/Worldkiln-zh-CN/releases/tag/win11-v1.0.1) |
| 1.1.0 | **预发布版（Pre-release）** | [下载 1.1.0](https://github.com/Aeowun/Worldkiln-zh-CN/releases/tag/win11-v1.1.0) |

每个版本包含原始 `Installer.exe` 和该版本附带的其他资源（如适用），均从 [Worldkiln 官方 Releases](https://github.com/Aeowun/Worldkiln/releases) 原样复制。每个发布页的说明中提供安装程序的 **SHA-256** 校验值。

## 许可证

Worldkiln 原始源代码使用 **Apache License, Version 2.0**，第三方组件及附带资源受各自许可证约束。本仓库保留[英文原版许可证](LICENSE)作为法律依据；中文解释不替代许可证原文。

## 翻译状态

这是未经中文母语专家审核的 AI 辅助初译，可能落后于英文官方文档。欢迎通过 [Pull Request](CONTRIBUTING.md) 协助改善准确性、自然度与一致性。
