# gogoga icons

[English](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/README.md) | **简体中文**

[gogoga](https://github.com/JackWeiGogoga/gogoga-theme) Obsidian 主题的配套插件。它通过
Obsidian 的 `addIcon()` API，把约 110 个 Obsidian 内置的 Lucide 界面图标替换为
[Phosphor Icons](https://phosphoricons.com/)（regular 字重）——也就是 Tolaria 使用的图标集。

## 安装

### 插件市场（推荐）

设置 → 第三方插件 → 关闭「安全模式」（新版叫「受限模式」）→ 点「浏览」，搜索 **gogoga icons**，安装后点「启用」。以后有新版本也在这里更新。

### 手动安装

不能联网（比如公司内网）、或者想装指定版本时用：

1. 打开 [Releases 页面](https://github.com/JackWeiGogoga/gogoga-icons/releases/latest)，在 **Assets** 里下载 `main.js`、`manifest.json` 这两个文件。**不要下载 Source code 压缩包**：那是源码，Obsidian 用不了。
2. 打开你的库（vault）所在文件夹，进到 `.obsidian/plugins/`，新建一个叫 `gogoga-icons` 的文件夹，把下载的文件放进去，最后是 `<库>/.obsidian/plugins/gogoga-icons/main.js` 这样的路径。
   - `.obsidian` 是隐藏文件夹：macOS 在访达里按 `⌘ ⇧ .` 显示；Windows 在资源管理器的「查看」里勾选「隐藏的项目」。
3. 重启 Obsidian（或在 设置 → 第三方插件 里点刷新按钮），在「已安装插件」列表里启用 **gogoga icons**。

手机上不方便放文件，建议用插件市场装。

## 开发

`main.js` 是生成的文件，请勿手动编辑。映射表在 `gen-icons.mjs` 里（`MAP`：
Obsidian/Lucide 图标 id → Phosphor 图标名）。修改或扩展映射表：

```bash
npm install
npm run generate
```

生成器从 `@phosphor-icons/core` 读取 SVG（regular 字重），把它们从 Phosphor 的
256 网格缩放到 Obsidian 的 100 网格，再注册到内置图标 id 上（裸 id 和带 `lucide-`
前缀的 id 都会注册）。

禁用插件后，重启应用即可恢复原始图标（`addIcon` 没有注销 API）。

## 支持作者

gogoga 系列全部免费开源。如果这个插件帮到了你，欢迎在 [爱发电](https://afdian.com/a/jackweigogoga) 支持一下，Obsidian 社区插件页面里也有赞助按钮。反馈 bug、提建议同样是很大的支持。

## 更新日志

每个版本的变化见 [CHANGELOG.zh-CN.md](CHANGELOG.zh-CN.md)（[English](CHANGELOG.md)）。发版前先写好新版本的条目：Release 说明从这里取，没写时发布会失败。

## 许可证

本插件采用 MIT 许可证（见 [LICENSE](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/LICENSE)）。
内置的图标素材来自 [Phosphor Icons](https://github.com/phosphor-icons/core)，
Copyright (c) 2023 Phosphor Icons，同样采用 MIT 许可证。
