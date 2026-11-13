# Worldkiln 功能介绍

[返回首页](README.md) · [下载](https://github.com/Aeowun/Worldkiln/releases) · [官方用户指南](https://aeowun.com/worldkiln/dive/)

Worldkiln 将 3D 世界编辑器、**AeoScript** 游戏逻辑和 Windows 独立游戏打包功能整合到一起。

> **翻译说明：** 本文由 AI 辅助翻译，尚未经过中文母语人士全面校对。发现错误时，请参阅[英文原文](https://github.com/Aeowun/Worldkiln/blob/master/FEATURES.md)，并通过[拉取请求](CONTRIBUTING.md)提出修正。

## 世界与环境

**Cells（构建单元）** 是 Worldkiln 用于搭建建筑、平台、室内空间和细节物体的基本元素。可以直接在视口中放置、删除、选取和变换 Cells。

**Landscaping（地形工具，BETA）** 包括地形生成、雕刻、平滑、压平和材质绘制功能。可以配合海岸线和大气环境设置创建场景。

**Water（水体，BETA）** 可表现动画波浪、碰撞引起的涟漪与尾迹、岸边水花和泡沫、表面湿润效果，以及摄像机浸入水下时随水面变化的视觉效果。

**材质与光照** 控制 Cells、Actors、地形、天空和水面的外观。距离雾效和粒子效果可以增强场景氛围。较新的材质编辑工具标注为 **BETA**。

## Actors 与资源

导入 **GLB 模型** 并作为 **Actors** 放入场景。可以布置和变换道具、配置碰撞，并使用带动画的 **Character** 资源包。

**Asset Manager（资源管理器）** 与 **Content Browser（内容浏览器）** 用于整理模型、纹理、音频、媒体、脚本和其他项目资源。编辑器中的部分资源字段支持拖放操作。

## 游戏逻辑

**AeoScript** 可以将游戏玩法连接到 World：查询对象、处理输入与事件、控制移动和摄像机、构建 UI、播放音频、驱动动画以及管理游戏状态。脚本可作为 **Modules** 重用，也可附加到游戏对象上。

Worldkiln 提供用于 **Characters** 和 **Actors** 的物理及导航能力，包括碰撞事件、路径查询和基于导航的行为。

可以使用 **Panels、Text、Buttons** 创建游戏 UI，也可以把音频发射器与粒子效果添加到场景中，并通过 AeoScript 控制运行时行为。

游戏进度可通过 AeoScript 的 `save` API 保存；这些数据与编辑器中保存的场景相互独立。

## 从编辑到游戏

使用 **Play** 模式测试移动、碰撞、脚本、摄像机和用户界面。使用 **Build Game** 将项目导出为可独立运行的 Windows 游戏。

更多信息请参阅[快速入门](GETTING_STARTED.md)、[AeoScript 指南](AEOSCRIPT.md)和[官方 API 参考](https://aeowun.com/docs/reference/)。

**BETA** 表示该功能仍在开发中。此页面介绍来自英文仓库，具体可用功能应以所使用的 Worldkiln 版本为准。
