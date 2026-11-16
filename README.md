# gogoga Icons

**English** | [简体中文](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/README.zh-CN.md)

Companion plugin for the [gogoga](https://github.com/JackWeiGogoga/gogoga-theme) Obsidian theme. It replaces ~110 of
Obsidian's built-in Lucide UI icons with [Phosphor Icons](https://phosphoricons.com/)
(regular weight) — the icon set used by Tolaria — via Obsidian's `addIcon()` API.

## Install

### Community plugins (recommended)

Settings → Community plugins → turn off **Restricted mode** → **Browse**, search for **gogoga Icons**, install it, then click **Enable**. Updates show up there too.

### Manual install

For offline machines (such as a company network) or to pin a specific version:

1. Open the [Releases page](https://github.com/JackWeiGogoga/gogoga-icons/releases/latest) and download the two files `main.js`, `manifest.json` under **Assets**. **Don't download the Source code archives**: they are the source code, which Obsidian can't load.
2. In your vault's folder, go to `.obsidian/plugins/`, create a folder named `gogoga-icons`, and put the files in it, so you end up with paths like `<vault>/.obsidian/plugins/gogoga-icons/main.js`.
   - `.obsidian` is a hidden folder: press `⌘ ⇧ .` in Finder on macOS; on Windows, tick **Hidden items** under **View** in File Explorer.
3. Restart Obsidian (or click the refresh button under Settings → Community plugins), then enable **gogoga Icons** in the list of installed plugins.

On phones, where moving files around is awkward, use the community plugins browser.

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

## Community

Bugs and feature requests: please open an [issue](https://github.com/JackWeiGogoga/gogoga-icons/issues) with a screenshot or recording and the version. Chinese-speaking users can also join the WeChat group: add `JackWeiGogoga` with the note “gogoga”, or scan the QR code on the [community page](https://obsidian.gogoga.top/en/community/).

## Support

gogoga is free and open source. If this plugin helps you, you can support its development on [afdian (爱发电)](https://afdian.com/a/jackweigogoga). Obsidian also shows a support button for it in the community directory. Bug reports and ideas help just as much.

## Changelog

What changed in each version is in [CHANGELOG.md](CHANGELOG.md) ([中文](CHANGELOG.zh-CN.md)). Add the new version there before releasing: the release notes are taken from it, and the release fails when the entry is missing.

## Licenses

This plugin is MIT licensed (see [LICENSE](https://github.com/JackWeiGogoga/gogoga-icons/blob/main/LICENSE)). The bundled icon
artwork comes from [Phosphor Icons](https://github.com/phosphor-icons/core),
Copyright (c) 2023 Phosphor Icons, also under the MIT License.
