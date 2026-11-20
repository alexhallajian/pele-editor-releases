# Customization examples

Paste an example into a new Obsidian note, render it, then right-click a node or the chart and choose Customize. Start with Mindmap, Radar, Pie and Flowchart. The remaining examples cover the rest of the audited types.

## Mindmap

```mermaid
mindmap
  root((Project))
    a[Collect]
      first(Notes)
      second(Research)
    b[Review]
      final[Publish]
```

## Radar

```mermaid
radar-beta
  title Comparison
  axis q["Quality"], p["Price"], s["Service"]
  curve a["Option A"]{8, 6, 9}
  curve b["Option B"]{6, 8, 7}
  min 0
  max 10
```

## Pie

```mermaid
pie title Acquisition
  "Search" : 45
  "Direct" : 35
  "Referral" : 20
```

## Flowchart

```mermaid
flowchart LR
  subgraph work[Work]
    a[Collect] --> b{Review}
  end
  b -->|Ready| c[Publish]
  b -->|Retry| a
```

## Agentflow

Right-click a node → Customize → Node shape. Try all six native shapes; each should change the actual geometry.

```mermaid
agentflow-beta TB
  a[Collect] --> b[Review]
  b --> c[Publish]
```

## Architecture

Right-click a service or the API group header → Customize → Service icon / Group icon. Try Cloud, Database, Disk, Internet, Server and No icon. Use original icon restores the initial icon.

```mermaid
architecture-beta
  group platform(cloud)[API platform]
  service api(server)[API] in platform
  service db(database)[Data] in platform
  api:R --> L:db
```

## Block

```mermaid
block
  columns 2
  a["Collect"] b["Review"]
  c["Publish"]:2
  a --> b
```

## C4

```mermaid
C4Context
  Person(user, "User")
  System(app, "Application")
  System_Ext(mail, "Mail")
  Rel(user, app, "Uses")
  Rel(app, mail, "Sends")
```

## Class

```mermaid
classDiagram
  class Request {
    +String title
    +submit()
  }
  class Review
  Request --> Review
```

## Cynefin

```mermaid
cynefin-beta
  title Decisions
  complex
  complicated
  clear
  chaotic
```

## Entity relationship

```mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  CUSTOMER {
    int id PK
    string name
  }
  ORDER {
    int id PK
    int customer_id FK
  }
```

## Event Modeling

```mermaid
eventmodeling
  tf 01 ui Form
  tf 02 cmd Submit
  tf 03 evt Submitted
```

## Gantt

```mermaid
gantt
  dateFormat YYYY-MM-DD
  section Work
  Collect :a, 2026-01-01, 3d
  Review :b, after a, 2d
  Publish :c, after b, 1d
```

## Git Graph

```mermaid
gitGraph
  commit id: "Start"
  branch feature
  commit id: "Change"
  checkout main
  merge feature
```

## Ishikawa

```mermaid
ishikawa-beta
  Delay
  Process
    Approval
    Scheduling
  Equipment
    Availability
```

## User Journey

```mermaid
journey
  title Review process
  section Work
    Collect: 4: Alex
    Review: 3: Alex, Sam
    Publish: 5: Sam
```

## Kanban

```mermaid
kanban
  todo[To do]
    a[Collect]
    b[Review]
  done[Done]
    c[Publish]
```

## Packet

```mermaid
packet
  title Message
  +8: "Type"
  +8: "Flags"
  +16: "Length"
  +32: "Body"
```

## Quadrant

```mermaid
quadrantChart
  title Priorities
  x-axis Low effort --> High effort
  y-axis Low impact --> High impact
  quadrant-1 Plan
  quadrant-2 Do
  quadrant-3 Delegate
  quadrant-4 Delay
  Task A: [0.2, 0.8]
  Task B: [0.7, 0.4]
```

## Railroad

```mermaid
railroad-ebnf-beta
  request = method, path ;
  method = "GET" | "POST" ;
```

## Requirement

```mermaid
requirementDiagram
  requirement fast {
    id: 1
    text: Quick response
    risk: low
    verifymethod: test
  }
  element api {
    type: service
  }
  api - satisfies -> fast
```

## Sankey

```mermaid
sankey
  Search,Visits,45
  Direct,Visits,35
  Referral,Visits,20
  Visits,Sales,30
  Visits,Exit,70
```

## Sequence

```mermaid
sequenceDiagram
  participant User
  participant API
  participant Unused
  User->>API: Request
  Note right of API: Review
  API-->>User: Response
  API->>API: Log
```

## State

```mermaid
stateDiagram-v2
  [*] --> Draft
  Draft --> Review
  Review --> Published
  Published --> [*]
```

## Swimlane

```mermaid
swimlane-beta
  subgraph Sales
    a[Collect] --> b[Review]
  end
  subgraph Delivery
    c[Publish]
  end
  b --> c
```

## Timeline

Right-click → Customize → Diagram settings → Layout → Direction → Top to bottom, then switch to Left to right.

```mermaid
timeline
  title Delivery
  section Plan
    Week 1 : Collect : Review
  section Ship
    Week 2 : Publish
```

## Treemap

```mermaid
treemap-beta
  "Acquisition"
    "Search": 45
    "Direct": 35
  "Other"
    "Referral": 20
```

## Tree View

```mermaid
treeView-beta
  "Project"
    "Research"
      "Notes.md"
    "Review.md"
```

## Use Case

```mermaid
usecase-beta
  actor User
  Review
  Publish
  User --> Review
  Review --> Publish
```

## Venn

```mermaid
venn-beta
  set A["Research"]
  set B["Delivery"]
  union A,B["Both"]
```

## Wardley

```mermaid
wardley-beta
  title Service map
  anchor User [0.9, 0.1]
  component API [0.6, 0.4]
  User -> API
```

## XY chart

```mermaid
xychart
  title "Quarterly sales"
  x-axis [Q1, Q2, Q3, Q4]
  y-axis "Sales" 0 --> 100
  bar [25, 45, 65, 80]
  line [30, 50, 60, 90]
```

