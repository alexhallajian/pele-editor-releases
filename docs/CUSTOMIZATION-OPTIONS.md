# Diagram customization reference

Pele Editor 1.3.0. Audited against Pele 1.13.0, including the examples published at [pele.run/examples](https://pele.run/examples), their source corpus, and the actual parsers/renderers. This lists the presentation controls exposed by Pele Editor; it is not a claim that every Mermaid configuration key or content-editing command works in Pele.

Right-click → Customize. Node-shape controls apply to the clicked node. Controls under **Diagram settings** apply to the whole diagram. On mobile, tap through the menus. Existing color, image-export and animation actions remain in the main menu.

## Coverage

| Diagram | Element controls | Diagram settings |
| --- | --- | --- |
| Agentflow | 6 native node shapes | 6: Layout, Connectors, Labels |
| Architecture | 5 built-in icons or No icon, for services/groups | 3: Services, Labels, Layout |
| Block | 14 ordinary-block shapes | 1: Layout |
| C4 | — | 2: Layout |
| Class | — | 5: Layout, Classes |
| Cynefin | — | 4: Labels, Boundaries, Layout |
| Entity relationship | — | 3: Layout |
| Event Modeling | — | No additional presentation controls found |
| Flowchart | 53 ordinary-node shapes | 5: Layout, Connectors, Labels |
| Gantt | — | 12: Layout, Axis, Tasks, Labels, Sections |
| Git Graph | — | 5: Layout, Labels |
| Ishikawa | — | No additional presentation controls found |
| User Journey | — | No additional presentation controls found |
| Kanban | — | 1: Columns |
| Mindmap | 7 root/node shapes | 1: Labels |
| Packet | — | 7: Bits, Layout |
| Pie | — | 4: Legend, Slices |
| Quadrant | — | 11: Layout, Axes, Points, Spacing |
| Radar | — | 14: Grid, Legend, Scale, Curves, Axes, Layout |
| Railroad | — | 8: Markers, Tracks, Layout, Labels |
| Requirement | — | 1: Layout |
| Sankey | — | 10: Labels, Layout, Flows |
| Sequence | — | 11: Participants, Messages, Notes, Layout |
| State | — | 5: Layout, Connectors, Labels |
| Swimlane | 53 ordinary-node shapes | 5: Layout, Connectors, Labels |
| Timeline | — | 2: Layout, Sections |
| Treemap | — | 5: Labels, Layout |
| Tree View | — | 4: Layout, Connectors |
| Use Case | — | 3: Layout |
| Venn | Set and overlap appearance; overlap fill color | 5: All sets |
| Wardley | — | 3: Grid, Layout |
| XY chart | — | 14: Layout, Labels, Legend, X axis, Y axis |

Event Modeling, Ishikawa and User Journey keep their existing color/export/animation menus and do not show an empty Customize submenu.

Desktop Pele Editor menus use OS-native handling at every nesting level to avoid stuck sibling submenus in Obsidian's DOM renderer. Mobile uses tappable follow-up menus. This only affects Pele Editor's context menus.

## Venn appearance

Right-click a circle or its main label for **Set appearance**. Right-click a declared overlap or its main label for **Overlap appearance**. Right-clicking the chart background still offers **Diagram settings → All sets**. The native Venn renderer ignores diagram configuration for these properties; Pele Editor writes native `style` statements to the targeted set or intersection.

| Control | Applies to | Native property |
| --- | --- | --- |
| Fill opacity (%) | Selected set/overlap, or all sets | `fill-opacity` |
| Outline width | Selected set/overlap, or all sets | `stroke-width` |
| Outline pattern: solid, dashed, dotted | Selected set/overlap, or all sets | `stroke-dasharray` |
| Bold label | Selected set/overlap, or all sets | `font-weight` |
| Italic label | Selected set/overlap, or all sets | `font-style` |
| Fill color | Selected overlap | `fill` |

An overlap color starts at 20% opacity unless its source already defines opacity. Outlines on an unstyled overlap use the current text color. Existing authored styles are preserved; Reset appearance removes only Pele Editor's overrides for the selected region. Reset diagram settings keeps individual-region overrides. All sets targets the currently declared circles when applied; applying a setting again includes newly added sets. An explicit All sets choice replaces the same saved property on individual circles. Other properties and overlap styling remain intact; a later per-set choice takes precedence for that circle. Quoted set IDs, including commas and pipes, remain separate. Ambiguous SVG IDs do not select an arbitrary region.

## Shapes

### Mindmap

Default, Rectangle, Rounded rectangle, Circle, Cloud, Bang, Hexagon.

### Flowchart and Swimlane

Rectangle, Rounded rectangle, Pill, Diamond, Circle, Double circle, Hexagon, Text, Subroutine, Cylinder, Data store, Folder, Bucket, Console, Browser, Person, Document, Stacked documents, Lined document, Tagged document, Tagged rectangle, Stacked rectangles, Notched rectangle, Lined rectangle, Divided rectangle, Window pane, Sloped rectangle, Parallelogram right, Parallelogram left, Trapezoid, Inverted trapezoid, Triangle, Inverted triangle, Notched pentagon, Bow tie, Hourglass, Delay, Horizontal cylinder, Lined cylinder, Display, Small circle, Filled circle, Stop, Crossed circle, Fork, Flag, Lightning bolt, Arrow rectangle, Cloud, Bang, Brace left, Brace right, Braces.

### Agentflow

Rounded rectangle (Task), Subroutine (Tool), Parallelogram (Input), Diamond (Decision), Lined document (Reference), Hexagon (Action). These use Agentflow’s semantic shape aliases. Agentflow deliberately reduces most ordinary flowchart shapes to its task shape, so those choices are not offered. Existing test-build overrides remain readable and can be replaced or removed with Use original shape.

### Block

Rectangle, Rounded rectangle, Circle, Double circle, Diamond, Hexagon, Pill, Subroutine, Cylinder, Parallelogram right, Parallelogram left, Trapezoid, Inverted trapezoid, Arrow rectangle.

Mindmap Default uses the renderer’s automatic root/branch/leaf appearance. Flowchart, Agentflow and block shape overrides can be removed with Use original shape. Image/icon nodes, group boundaries and block arrows keep their specialized rendering. Flowchart/block nodes need a simple native ID; a shape choice is omitted when safe targeting is unavailable.

## Architecture icons

Right-click a service icon/label → Customize → Service icon, or a group boundary/header → Customize → Group icon. Cloud, Database, Disk, Internet and Server are built into Pele and work offline. No icon removes the glyph. Junctions and the chart background do not have icon choices.

An icon choice edits only the clicked element’s native declaration. Labels, parents, connections, layout hints, color settings and other icons stay intact. Use original icon restores the exact authored glyph token, including custom icon-pack IDs and service text icons. Reset diagram settings keeps per-element icons. Label/layout edits made afterward remain intact when an icon is reset. Manually changing the owned icon token is detected before another Customize edit is saved.

## Diagram settings

### Agentflow

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.agentflow.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.agentflow.rankSpacing |
| Connectors | Connector curves | Smooth, Straight, Right angles, Step before, Step after | config.flowchart.curve |
| Labels | Label wrapping width | 1–2000 | config.agentflow.wrappingWidth |
| Layout | Minimum node width | 1–2000 | config.agentflow.minNodeWidth |

### Architecture

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Services | Icon size | 8–256 | config.architecture.iconSize |
| Labels | Label size | 4–128 | config.architecture.fontSize |
| Layout | Service padding | 0–200 | config.architecture.padding |

### Block

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Block padding | 0–200 | config.block.padding |

### C4

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Elements per row | 1–50 (whole numbers) | c4.shapeInRow |
| Layout | Boundaries per row | 1–50 (whole numbers) | c4.boundaryInRow |

### Class

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.class.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.class.rankSpacing |
| Classes | Hide empty member boxes | On / off | config.class.hideEmptyMembersBox |
| Classes | Nested namespaces | On / off | config.class.hierarchicalNamespaces |

### Cynefin

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Labels | Show domain descriptions | On / off | config.cynefin.showDomainDescriptions |
| Boundaries | Boundary waviness | 0–50 | config.cynefin.boundaryAmplitude |
| Layout | Width | 100–4000 | config.cynefin.width |
| Layout | Height | 100–4000 | config.cynefin.height |

### Entity relationship

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.er.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.er.rankSpacing |

### Flowchart

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.flowchart.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.flowchart.rankSpacing |
| Connectors | Connector curves | Smooth, Straight, Right angles, Step before, Step after | config.flowchart.curve |
| Labels | Label wrapping width | 1–2000 | config.flowchart.wrappingWidth |

### Gantt

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Task layout | Separate rows, Compact | config.gantt.displayMode |
| Axis | Show top axis | On / off | config.gantt.topAxis |
| Tasks | Task height | 4–400 | config.gantt.barHeight |
| Tasks | Task spacing | 0–400 | config.gantt.barGap |
| Labels | Task label size | 4–72 | config.gantt.fontSize |
| Labels | Section label size | 4–72 | config.gantt.sectionFontSize |
| Sections | Alternating section styles | 1–1000 | config.gantt.numberSectionStyles |
| Layout | Chart width | 100–20000 | config.gantt.useWidth |
| Layout | left Padding | 0–2000 | config.gantt.leftPadding |
| Layout | right Padding | 0–2000 | config.gantt.rightPadding |
| Layout | top Padding | 0–2000 | config.gantt.topPadding |
| Layout | grid Line Start Padding | 0–2000 | config.gantt.gridLineStartPadding |

### Git Graph

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right | gitGraph.direction |
| Labels | Show branch names | On / off | config.gitGraph.showBranches |
| Labels | Show commit labels | On / off | config.gitGraph.showCommitLabel |
| Labels | Rotate commit labels | On / off | config.gitGraph.rotateCommitLabel |
| Layout | Align parallel commits | On / off | config.gitGraph.parallelCommits |

### Kanban

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Columns | Column width | 80–2000 | config.kanban.sectionWidth |

### Mindmap

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Labels | Maximum node width | 1–2000 | config.mindmap.maxNodeWidth |

### Packet

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Bits | Show bit numbers | On / off | config.packet.showBits |
| Bits | Bit order | ascending, descending | config.packet.bitOrder |
| Layout | Bits per row | 1–4096 (whole numbers) | config.packet.bitsPerRow |
| Layout | Row height | 1–400 | config.packet.rowHeight |
| Layout | Bit width | 1–400 | config.packet.bitWidth |
| Layout | Horizontal label padding | 0–400 | config.packet.paddingX |
| Layout | Vertical label padding | 0–400 | config.packet.paddingY |

### Pie

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Legend | Show values in legend | On / off | pie.showData |
| Slices | Donut hole | None, Small, Medium, Large | config.pie.donutHole |
| Slices | Percentage label position | 0–1 | config.pie.textPosition |
| Legend | Legend position | right, bottom, left, top, center | config.pie.legendPosition |

### Quadrant

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Width | 100–4000 | config.quadrantChart.chartWidth |
| Layout | Height | 100–4000 | config.quadrantChart.chartHeight |
| Axes | X axis position | top, bottom | config.quadrantChart.xAxisPosition |
| Axes | Y axis position | left, right | config.quadrantChart.yAxisPosition |
| Points | Default point radius | 0–200 | config.quadrantChart.pointRadius |
| Points | Point label distance | 0–200 | config.quadrantChart.pointTextPadding |
| Spacing | quadrant Padding | 0–200 | config.quadrantChart.quadrantPadding |
| Spacing | x Axis Label Padding | 0–200 | config.quadrantChart.xAxisLabelPadding |
| Spacing | y Axis Label Padding | 0–200 | config.quadrantChart.yAxisLabelPadding |
| Spacing | title Padding | 0–200 | config.quadrantChart.titlePadding |
| Spacing | quadrant Text Top Padding | 0–200 | config.quadrantChart.quadrantTextTopPadding |

### Radar

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Grid | Grid shape | Circular, Polygon | radar.graticule |
| Grid | Grid rings | 0–32 (whole numbers) | radar.ticks |
| Legend | Show legend | On / off | radar.showLegend |
| Scale | Minimum value | 0–1000000000 | radar.min |
| Scale | Maximum value | 0.001–1000000000 | radar.max |
| Curves | Curve smoothing | 0–1 | config.radar.curveTension |
| Axes | Axis length | 0–10 | config.radar.axisScaleFactor |
| Axes | Axis label distance | 0–10 | config.radar.axisLabelFactor |
| Layout | Width | 100–4000 | config.radar.width |
| Layout | Height | 100–4000 | config.radar.height |
| Layout | Top margin | 0–2000 | config.radar.marginTop |
| Layout | Right margin | 0–2000 | config.radar.marginRight |
| Layout | Bottom margin | 0–2000 | config.radar.marginBottom |
| Layout | Left margin | 0–2000 | config.radar.marginLeft |

### Railroad

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Markers | Show endpoint markers | On / off | config.railroad.showMarkers |
| Markers | Marker radius | 0–50 | config.railroad.markerRadius |
| Tracks | Track thickness | 0.1–20 | config.railroad.strokeWidth |
| Tracks | Turn radius | 0–200 | config.railroad.arcRadius |
| Layout | Horizontal spacing | 0–500 | config.railroad.horizontalSeparation |
| Layout | Vertical spacing | 0–500 | config.railroad.verticalSeparation |
| Labels | Label size | 1–200 | config.railroad.fontSize |
| Labels | Label padding | 0–200 | config.railroad.padding |

### Requirement

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |

### Sankey

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Labels | Show values | On / off | config.sankey.showValues |
| Layout | Node alignment | justify, left, right, center | config.sankey.nodeAlignment |
| Flows | Flow colors | gradient, source, target | config.sankey.linkColor |
| Labels | Label style | Plain, Outlined | config.sankey.labelStyle |
| Labels | Value prefix | Text, up to 120 characters | config.sankey.prefix |
| Labels | Value suffix | Text, up to 120 characters | config.sankey.suffix |
| Layout | Width | 100–4000 | config.sankey.width |
| Layout | Height | 100–4000 | config.sankey.height |
| Layout | Node width | 1–200 | config.sankey.nodeWidth |
| Layout | Node spacing | 0–200 | config.sankey.nodePadding |

### Sequence

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Participants | Repeat participants at bottom | On / off | config.sequence.mirrorActors |
| Participants | Hide unused participants | On / off | config.sequence.hideUnusedParticipants |
| Messages | Number messages | On / off | config.sequence.showSequenceNumbers |
| Messages | Right-angle self messages | On / off | config.sequence.rightAngles |
| Messages | Message alignment | left, center, right | config.sequence.messageAlign |
| Participants | Participant spacing | 1–2000 | config.sequence.actorMargin |
| Participants | Participant width | 1–2000 | config.sequence.width |
| Participants | Participant height | 1–2000 | config.sequence.height |
| Messages | Message spacing | 1–2000 | config.sequence.messageMargin |
| Notes | Note padding | 1–2000 | config.sequence.noteMargin |
| Layout | Box padding | 1–2000 | config.sequence.boxMargin |

### State

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.state.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.state.rankSpacing |
| Connectors | Connector curves | Smooth, Straight, Right angles, Step before, Step after | config.flowchart.curve |
| Labels | Label wrapping width | 1–2000 | config.state.wrappingWidth |

### Swimlane

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.swimlane.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.swimlane.rankSpacing |
| Connectors | Connector curves | Smooth, Straight, Right angles, Step before, Step after | config.swimlane.curve |
| Labels | Label wrapping width | 1–2000 | config.swimlane.wrappingWidth |

### Timeline

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Left to right, Top to bottom | Native `timeline LR` / `timeline TD` header |
| Sections | Use one section color | On / off | config.timeline.disableMulticolor |

### Treemap

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Labels | Show values | On / off | config.treemap.showValues |
| Labels | Value format | Text, up to 120 characters | config.treemap.valueFormat |
| Layout | Chart width scale | 1–400 | config.treemap.nodeWidth |
| Layout | Chart height scale | 1–400 | config.treemap.nodeHeight |
| Layout | Tile spacing | 0–200 | config.treemap.padding |

### Tree View

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Indentation | 0–400 | config.treeView.rowIndent |
| Connectors | Connector thickness | 0.25–12 | config.treeView.lineThickness |
| Layout | Horizontal padding | 0–100 | config.treeView.paddingX |
| Layout | Vertical padding | 0–100 | config.treeView.paddingY |

### Use Case

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Direction | Top to bottom, Bottom to top, Left to right, Right to left | Diagram direction |
| Layout | Node spacing | 1–2000 | config.usecase.nodeSpacing |
| Layout | Level spacing | 1–2000 | config.usecase.rankSpacing |

### Wardley

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Grid | Show grid | On / off | config.wardley-beta.showGrid |
| Layout | Width | 100–4000 | config.wardley-beta.width |
| Layout | Height | 100–4000 | config.wardley-beta.height |

### XY chart

| Group | Control | Choices or input | Native setting |
| --- | --- | --- | --- |
| Layout | Orientation | vertical, horizontal | xychart.orientation |
| Labels | Show data values | On / off | config.xyChart.showDataLabel |
| Labels | Show title | On / off | config.xyChart.showTitle |
| Legend | Show legend | On / off | config.xyChart.showLegend |
| Layout | Width | 100–4000 | config.xyChart.width |
| Layout | Height | 100–4000 | config.xyChart.height |
| X axis | Show axis title | On / off | config.xyChart.xAxis.showTitle |
| X axis | Show tick labels | On / off | config.xyChart.xAxis.showLabel |
| X axis | Show tick marks | On / off | config.xyChart.xAxis.showTick |
| X axis | Show axis line | On / off | config.xyChart.xAxis.showAxisLine |
| Y axis | Show axis title | On / off | config.xyChart.yAxis.showTitle |
| Y axis | Show tick labels | On / off | config.xyChart.yAxis.showLabel |
| Y axis | Show tick marks | On / off | config.xyChart.yAxis.showTick |
| Y axis | Show axis line | On / off | config.xyChart.yAxis.showAxisLine |

## Persistence and reset

Diagram options are stored in a marked customization section inside the Mermaid block. They use native init configuration and native diagram statements. Existing front matter, init directives, color palettes and unrelated source remain intact. Header-only settings retain the original header for reset. Mindmap shapes edit only the clicked node’s delimiters; the label, indentation and decorations are checked before saving.

Use default removes one saved option. Reset diagram settings removes saved diagram options while keeping colors and node-shape overrides. Flowchart/block nodes have Use original shape. The normal editor undo history applies to Live Preview saves. Invalid, incomplete or manually changed generated sections and stale source snapshots are rejected instead of overwritten.

Pele adapts layouts to narrow containers, so an explicit shape or width may look different when the diagram is folded into its narrow-screen layout. The original data, relationships and declared styling remain in the source.

## Source references

- [Pele examples and how they are assembled](https://github.com/obsidianmd/pele/blob/main/website/src/lib/examples.ts)
- [Every documented example, by diagram](https://github.com/obsidianmd/pele/tree/main/tests/corpus)
- [Parsers and renderers](https://github.com/obsidianmd/pele/tree/main/src/diagrams)
- [Native config/directive precedence](https://github.com/obsidianmd/pele/blob/main/src/preprocess.ts)
- [Mindmap shapes](https://github.com/obsidianmd/pele/blob/main/src/diagrams/common/outline.ts)
- [Radar options](https://github.com/obsidianmd/pele/blob/main/src/diagrams/radar/model.ts)

The in-app checks for this test build are in [CUSTOMIZATION-TESTING.md](CUSTOMIZATION-TESTING.md).
