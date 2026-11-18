# Pele Editor

Style and export Mermaid diagrams rendered by [Pele](https://pele.run/) in Obsidian. Right-click a diagram element to change its color, apply a gradient across related elements, pick a saved color preset, or export an image for a social post or presentation. Pele Editor writes styling back to the Mermaid block in your note.

## Trial and pricing

Pele Editor requires Obsidian 1.15.0 or later on desktop or mobile. In **Settings → Pele Editor**, choose **Start trial** to try editing and image export free for seven days. After the trial, a one-time purchase of **$5 USD** is required to continue changing diagram colors, managing presets, and exporting images. Diagrams keep displaying the styles you already saved.

To purchase, choose **Buy for $5** in the plugin settings. Dodo Payments emails your license key after purchase. Paste that key into **License key** and choose **Activate**.

## Privacy and network use

Pele Editor stores the trial start time, presets, and license activation in your vault's plugin settings. Diagram styles are written to your notes and rendered locally. Image export runs locally. It copies the selected diagram without changing your note or uploading it. Fonts available in the app are embedded when possible; export does not download remote fonts. On desktop, the save dialog writes only to the location you choose. On mobile, native sharing hands the image to the app you choose; the native bridge may keep a temporary image in the app cache. The explicit **Save to vault** fallback creates an image in **Pele exports**.

Dodo Payments handles checkout and license verification. During activation, the plugin sends your license key and the label “Pele Editor” to Dodo Payments. After activation, it sends the key and activation ID to verify access when the plugin starts and once a day while it stays enabled. A previously verified license keeps editing available if the service is temporarily unreachable. Your notes and diagrams stay in Obsidian during these checks.

## Quick start

1. Open a rendered Mermaid diagram in Obsidian's Reading view or Live Preview.
2. Right-click a supported element on desktop. On mobile, press and hold it for about half a second, then release. For example, open the menu on a timeline section header and choose **Section color…**.
3. Pick a color or choose one from the **Preset** dropdown, then click **Apply**.

Choose **Reset color** to return the element to its series color or the diagram default.

## Export images

Right-click anywhere inside a rendered diagram and choose **Export…**. On mobile, press and hold the diagram, then release. Export requires an active trial or license.

- **PNG** creates an image for Instagram, other social platforms, and slide presentations. Choose 1×, 2×, or 4× resolution. Very large images are reduced to a safe size for your device; the preview shows the output dimensions.
- **SVG** keeps the diagram as a scalable vector image for compatible presentation and design apps.
- Choose **Match Obsidian**, **Transparent**, or a custom **Solid color** background. Both formats support transparency. The preview's checkerboard is not included in the file.

The export captures the complete rendered diagram, including colors, gradients, labels, and layout. Panning and zooming do not crop it. On desktop, **Save as…** opens the operating system's save dialog. On mobile, **Share…** opens native file sharing when Obsidian and the operating system support it for the selected format. Available destinations depend on the device and installed apps. If sharing is unavailable, **Save to vault** saves a uniquely named file in **Pele exports** without replacing an existing export.

Check the preview before saving. Custom fonts that cannot be embedded may use a fallback, and receiving apps can differ in their SVG font support. Diagrams that reference external image files must embed those images first. For a social post with predictable background colors, use PNG with a solid background.

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

The original Pele Editor code is proprietary, and the source repository is private. See [LICENSE](LICENSE) for the usage terms and the licenses of the template and bundled components.

## Local development

Use Obsidian Desktop with Pele rendering. If you have access to the source repository, install dependencies and start the development build from that repository:

```sh
npm install
npm run dev
```

For local testing, place the generated `main.js`, `manifest.json`, and `styles.css` together in `.obsidian/plugins/pele-editor/` inside a test vault. The stylesheet displays the Color Series swatch preview. Enable **Pele Editor** under **Settings → Community plugins**. If the plugin is already enabled, reload it after replacing the build.
