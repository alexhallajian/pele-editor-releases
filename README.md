# Pele Editor

Style Mermaid diagrams rendered by [Pele](https://pele.run/) in Obsidian. Right-click a diagram element to change its color, apply a gradient across related elements, or pick a saved color preset. Pele Editor writes the styling back to the Mermaid block in your note.

## Trial and pricing

Pele Editor requires Obsidian 1.15.0 or later on desktop or mobile. In **Settings → Pele Editor**, choose **Start trial** to try all editing features free for seven days. After the trial, a one-time purchase of **$5 USD** is required to continue changing diagram colors and managing presets. Diagrams keep displaying the styles you already saved.

To purchase, choose **Buy for $5** in the plugin settings. Dodo Payments emails your license key after purchase. Paste that key into **License key** and choose **Activate**.

## Privacy and network use

Pele Editor stores the trial start time, presets, and license activation in your vault's plugin settings. Diagram styles are written to your notes and rendered locally.

Dodo Payments handles checkout and license verification. During activation, the plugin sends your license key and the label “Pele Editor” to Dodo Payments. After activation, it sends the key and activation ID to verify access when the plugin starts and once a day while it stays enabled. A previously verified license keeps editing available if the service is temporarily unreachable. Your notes and diagrams stay in Obsidian during these checks.

## Quick start

1. Open a rendered Mermaid diagram in Obsidian's Reading view or Live Preview.
2. Right-click a supported element on desktop. On mobile, press and hold it for about half a second, then release. For example, open the menu on a timeline section header and choose **Section color…**.
3. Pick a color or choose one from the **Preset** dropdown, then click **Apply**.

Choose **Reset color** to return the element to its series color or the diagram default.

## Color series

Choose **Color series…** from the same menu, pick a first and last color, and preview the gradient before applying it. Pele Editor spaces the colors across the elements in that series using OKLCH with the shorter hue path. When you add elements to a diagram, the series adjusts to fit.

Choose **Reverse colors** to swap the first and last colors. Both color controls and the preview swatches update immediately. Choose **Apply** to use the reversed gradient, or **Save as preset** to save it under a new name.

Applying a new series replaces individual color choices in that series. You can customize individual elements afterward.

## Color presets

Use **Save as preset** in the color picker to name a single color or a pair of gradient endpoints. You can also add, edit, and delete presets under **Color presets** in the plugin settings. Presets are available from the **Preset** dropdown when styling other diagrams.

The plugin includes four starter Color Series presets:

| Preset | First color | Last color |
| --- | --- | --- |
| Outrun | `#1d90d7` | `#c421bf` |
| Sunset | `#c21919` | `#c46517` |
| Flame | `#e37316` | `#143bd7` |
| Iceberg | `#8ebbf5` | `#0c32ed` |

Starter presets are added once when you install or upgrade. Existing presets are kept, including any Color Series preset with the same name. You can edit or delete the starter presets; they will not be restored on every restart. Reversing a preset in the picker changes the current gradient without changing the saved preset.

## Supported diagrams

Pele Editor supports the 32 diagram types in the [Pele examples](https://pele.run/examples), including flowcharts, timelines, sequence diagrams, Gantt charts, mindmaps, and architecture diagrams. Available color controls depend on the diagram type and the element you click.

## Software license

Pele Editor is proprietary software. This repository provides the compiled plugin files and public releases. The TypeScript source and development history are maintained in a separate private repository. See [LICENSE](LICENSE) for the usage terms and third-party notices.
