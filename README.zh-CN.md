# gogoga icons

[English](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/README.md) | **简体中文**

[gogoga](https://github.com/JackWeiGogoga/gogoga-theme) Obsidian 主题的配套插件。它通过
Obsidian 的 `addIcon()` API，把约 110 个 Obsidian 内置的 Lucide 界面图标替换为
[Phosphor Icons](https://phosphoricons.com/)（regular 字重）——也就是 Tolaria 使用的图标集。

## 安装

把 `main.js` 和 `manifest.json` 复制到
`<vault>/.obsidian/plugins/gogoga-icons/`，然后在
设置 → 第三方插件 中启用本插件（需要先关闭安全模式）。

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

## 许可证

本插件采用 MIT 许可证（见 [LICENSE](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/LICENSE)）。
内置的图标素材来自 [Phosphor Icons](https://github.com/phosphor-icons/core)，
Copyright (c) 2023 Phosphor Icons，同样采用 MIT 许可证。
