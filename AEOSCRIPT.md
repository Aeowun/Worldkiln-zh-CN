# AeoScript 简体中文指南

[返回首页](README.md) · [官方语言文档](https://aeowun.com/aeoscript/) · [API 参考](https://aeowun.com/docs/reference/)

**AeoScript** 是 Worldkiln 用于编写游戏行为的脚本语言。这里将介绍事件、变量、函数、对象与游戏状态。所有代码关键字及 API 名称均保留英文。

> **AI 翻译提示：** 开发者不懂中文。本文可能存在语言或技术错误，且不一定与最新版本同步。请以[英文原始说明](https://github.com/Aeowun/Worldkiln/blob/master/AEOSCRIPT.md)和[官方 API 参考](https://aeowun.com/docs/reference/)为准；欢迎[提交修正](CONTRIBUTING.md)。

## 事件示例

在 Worldkiln 项目中创建 `scripts/score.aeo`：

```aeoscript
score: number = 0

on coin_collected(points) {
    score += points
    debug.log("Score:", score)
}

event.fire("coin_collected", 10)
```

进入 **Play** 模式并打开 **Output**，就可以查看输出。事件处理函数收到数值后将其加到积分中，然后写入调试日志。

## 变量与函数

使用 `const` 定义不可更改的绑定。可变变量以名称和类型进行声明，对现有变量的赋值则会更新它的值。

```aeoscript
const BONUS = 5
total: number = 10

fn award(points) {
    total += points + BONUS
}

award(10)
```

AeoScript 还支持函数、闭包、集合、流程控制和 `wait()`。具体规则请参阅[语法](https://aeowun.com/aeoscript/syntax/)、[函数](https://aeowun.com/aeoscript/functions/)和[等待](https://aeowun.com/aeoscript/waiting/)。

## 脚本、Modules 与 Entities

| 类型 | 主要用途 |
| --- | --- |
| Project script | 全局事件、初始化和游戏系统 |
| Module | 可重用的函数及状态，包括附加到 Actor 的行为 |
| Entity script | 对象自身的属性和生命周期函数 |

引用其他 Module 的示例：

```aeoscript
const helper = scripts.game_helpers.aeo
```

Entity 可以定义自己的状态与更新函数：

```aeoscript
entity Counter {
    count: number = 0

    fn update(dt) {
        count += 1
    }
}
```

进一步阅读：[Modules](https://aeowun.com/aeoscript/modules/) 与 [Entity scripts](https://aeowun.com/aeoscript/entities/)。

## 查询世界中的对象

根据名称查找一个 Actor：

```aeoscript
const door = proj.find("Door")

if door != nil {
    debug.log(door)
}
```

世界交互相关 API 包括[对象查询](https://aeowun.com/aeoscript/find/)、[输入](https://aeowun.com/aeoscript/input/)、[UI](https://aeowun.com/aeoscript/ui/)、[音频](https://aeowun.com/aeoscript/audio/)和[事件](https://aeowun.com/aeoscript/events/)。

部分较新的 **BETA** API 涉及 Actor 标签、属性变化观察、地形表面查询与选定的材质动画功能。

## 保存游戏状态

停止 **Play** 后，运行期间的改动通常会重置。需要跨会话保留的数据可通过 `save` 处理：

```aeoscript
save.set("coins", 20)
save.commit()
```

之后可以通过 `save.get("coins")` 读取。详细用法请查看[存档文档](https://aeowun.com/aeoscript/save/)。

## 游戏生命周期

| API | 作用 |
| --- | --- |
| `game.quit()` | 发出 `game_on_quit` 信号，随后退出当前游戏实例或编辑器中的 Play |
| `game.restart()` | 在当前窗口重新加载游戏，并保留已保存的数据 |
| `game.pause()` | 暂停单人游戏模拟；多人游戏中会给出警告，不执行暂停 |
| `game.resume()` | 恢复单人游戏模拟 |
| `game.is_paused` | 当前是否处于暂停状态 |
| `game.elapsed_time` | 本次会话的有效游戏时间（秒） |
| `game.delta_time` | 最近一次更新的游戏时间增量（秒） |
| `game.is_editor` | 当前是否在编辑器 Play 中运行 |
| `game.is_standalone` | 当前是否在独立游戏窗口运行 |
| `game.on_quit` | 对应事件名 `game_on_quit` |
| `game.on_pause` | 对应事件名 `game_on_pause` |
| `game.on_resume` | 对应事件名 `game_on_resume` |

可在退出时由游戏自己的事件处理函数保存数据：

```aeoscript
on game_on_quit() {
    save.commit()
}
```

`game_on_quit` 仅是事件信号，实际保存与清理操作由游戏作者编写。`save.restart()` 只重置并提交存档数据，并不会重新启动游戏；`save.reset()` 保留原本的未提交重置行为。

## 网络邀请（V1.1.0 开发中的功能）

英文原文将以下接口标记为 **V1.1.0 开发功能**。请先检查安装的 Worldkiln 版本是否提供这些接口。

| API | 用途 |
| --- | --- |
| `network.host_invite(2)` | 异步请求通过中继建立会话；可选人数范围 2–8 |
| `network.join_invite(link)` | 通过 HTTPS 邀请链接或 32 字符邀请码加入 |
| `network.invite_link()` | 获取当前主机的分享链接；没有时返回空字符串 |
| `network.leave()` | 离开当前会话，回到单人模式 |
| `clipboard.write(link)` | 将文本写入系统剪贴板，成功时返回 true |
| `clipboard.read()` | 读取剪贴板中的文本 |

当中继准备好邀请时，主机会收到 `network_invite_ready(link)`；加入失败时会发出 `network_join_failed(reason)`：

```aeoscript
on network_invite_ready(link) {
    clipboard.write(link)
    debug.log("Invitation copied")
}

on network_join_failed(reason) {
    debug.log("Unable to join:", reason)
}
```

这些网络 API 并不意味着所有 Worldkiln 发布版本都已提供互联网多人游戏。官方参考资料和实际使用版本应作为最终依据。

## 查询最新 API

请到[官方 API 参考](https://aeowun.com/docs/reference/)查阅完整的函数名、参数和返回值；排查报错时阅读[诊断文档](https://aeowun.com/aeoscript/diagnostics/)。
