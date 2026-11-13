# Worldkiln 快速入门

[返回首页](README.md) · [功能介绍](FEATURES.md) · [AeoScript](AEOSCRIPT.md)

本指南帮助你完成初次安装、创建项目、构建简单场景和测试。内容基于 [Worldkiln 英文 README](https://github.com/Aeowun/Worldkiln/blob/master/README.md) 及[官方入门指南](https://aeowun.com/worldkiln/getting-started/)。不同版本的按钮名称或位置可能有所不同。

> **翻译声明：** 开发者不懂中文；本指南由 AI 辅助翻译。欢迎提交[拉取请求](CONTRIBUTING.md)修正语言或技术错误。

## 1. 下载并安装

1. 打开 Worldkiln 的 [GitHub Releases 页面](https://github.com/Aeowun/Worldkiln/releases)。
2. 下载最新版安装程序，以及需要的可选资源。
3. 安装 Worldkiln 并启动编辑器。

英文文档列出的支持平台为 **Windows 10 和 Windows 11**。

## 2. 新建项目

启动 Worldkiln 后，在编辑器中创建新项目，并选择保存项目文件的位置。

建议先建立一个简单的测试场景，熟悉编辑器的操作，再逐步加入其他功能。

## 3. 构建第一个场景

- 使用 **Cells** 搭建地面、平台或墙壁。
- 在视口中尝试选取、移动、旋转和调整对象大小。
- 修改材质和光照，观察场景外观的变化。
- 对于更大的地形，可探索 **Landscaping（BETA）** 工具。

## 4. 导入一个 3D 模型

推荐使用 **`.glb`** 文件。GLB 可以包含模型几何体、材质、纹理、骨架及动画。

使用 **Content Browser** 或 **Asset Manager** 整理项目资源，再把导入的模型作为 **Actor** 放置到场景中。

如果手头的模型是 FBX、OBJ 或 Blender 文件，英文 V1 导入说明建议先在 [Blender](https://www.blender.org/) 中导出为 **glTF Binary (`.glb`)**。最新版本的实际支持情况可能变化，请查看当前官方文档。

## 5. 使用 Play 模式测试

点击编辑器的 **Play** 功能，测试场景、碰撞、摄像机及 AeoScript 逻辑。

如果测试时看不到场景或无法控制角色，请先核对项目中的角色、出生位置和摄像机配置，确认场景设置正确。

## 6. 编写游戏逻辑

Worldkiln 使用 **AeoScript** 编写游戏逻辑。你可以通过事件控制对象互动，处理输入，或存储游戏状态。

参阅 [AeoScript 中文指南](AEOSCRIPT.md) 了解具体示例。

**请保留代码中的英文关键字和 API 名称。** 翻译注释和文档说明不等于更改语言本身的语法。

## 7. 导出独立游戏

当场景、玩家与摄像机配置好，并在 **Play** 中通过测试后，可以使用 **Build Game** 创建独立运行的 Windows 游戏。

导出完成后，应单独启动打包结果，检查脚本、资源与玩法是否正常运行，不要仅依赖编辑器中的测试结果。

## 更多参考

- [Worldkiln 官方入门指南](https://aeowun.com/worldkiln/getting-started/)
- [用户指南](https://aeowun.com/worldkiln/dive/)
- [AeoScript 官方文档](https://aeowun.com/aeoscript/)
- [API 参考](https://aeowun.com/docs/reference/)
- [技术支持](https://aeowun.com/support/)
