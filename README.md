# gogoga icons

**English** | [简体中文](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/README.zh-CN.md)

Companion plugin for the [gogoga](https://github.com/JackWeiGogoga/gogoga-theme) Obsidian theme. It replaces ~110 of
Obsidian's built-in Lucide UI icons with [Phosphor Icons](https://phosphoricons.com/)
(regular weight) — the icon set used by Tolaria — via Obsidian's `addIcon()` API.

## Install

Copy `main.js` and `manifest.json` into
`<vault>/.obsidian/plugins/gogoga-icons/`, then enable the plugin in
Settings → Community plugins (requires restricted mode off).

## Development

`main.js` is generated — do not edit it by hand. The mapping table lives in
`gen-icons.mjs` (`MAP`: Obsidian/Lucide icon id → Phosphor icon name). To
change or extend it:

```bash
npm install
npm run generate
```

The generator reads SVGs from `@phosphor-icons/core` (regular weight),
rescales them from Phosphor's 256 grid to Obsidian's 100 grid, and registers
them over the built-in icon ids (both bare and `lucide-`-prefixed).

Disabling the plugin restores the original icons after an app reload
(`addIcon` has no unregister API).

## Support

gogoga is free and open source. If this plugin helps you, you can support its development on [afdian (爱发电)](https://afdian.com/a/jackweigogoga). Obsidian also shows a support button for it in the community directory. Bug reports and ideas help just as much.

## Licenses

This plugin is MIT licensed (see [LICENSE](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/LICENSE)). The bundled icon
artwork comes from [Phosphor Icons](https://github.com/phosphor-icons/core),
Copyright (c) 2023 Phosphor Icons, also under the MIT License.
