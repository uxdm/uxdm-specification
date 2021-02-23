# Nodes Map

It's the basis of the whole project, with nodes, slots on nodes, and connections that connect slots. You can't push the project to the design phase until you have a clear nodes map for the project. The whole design needs to reflect the nodes map precisely.

Since the design reflects the whole map, prototyping after designing is no longer required. When you preview the design, you can easily navigate through the prototype.

## Node

A node is a single point of nodes map, which reflects a frame during design.

### Properties

- ID *
- Name *
- Description
- Default Slots *
  - Entry slot
  - Back
  - Root slots (If this is a root node)
- *[Slots]* *
  - Slot
- *[States]*
  - Name *
  - Slots *
    - Override
    - Deleted inherits
    - Inherits (Same as node defaults)

## Slot

Each node could have multiple slots. Each slot could have descriptions and properties. When a designer maps the slot to the design, it's the triggers that we need to map. So different user interactions can trigger the same slot connection.

### Properties

- ID *
- Name
- Description
- Exposed (Available if the node is inside a group)
- Type *
  - Single entry
  - Repeatable elements
  - Exposed slot (Only if this node is part of a group)
- Connection Type *
  - General
  - Previous
- *[Triggers]* * (Interactive trigger of the slot related connection, with types of the following)
  - Tap / Click
    - Fingers count
  - Right-click
  - Long-tap
  - Double-tap
  - Swipe
  - Swipe from the edge
  - Shake device
  - Custom triggers

## Navigation Node

For the app-level navigation system, we can set a root node. Once a project gets any root nodes, a Navigation Node is added to the project by default. **One cannot add Navigation Node manually.** Also, slots of the Navigation Node are directly linked to root nodes and cannot be added manually. Each root node will have root slots added to the default slots.

Each root node maps as a single Root Slot of Navigation Node. When designing, the Navigation Node has to map as a frame. All root slots must map as elements. We can add Custom elements in addition to root slots.

## States

A single node can have multiple states. Each state can have override slots on top of the default slots. And we can hide Inherited slots. Each state needs to map as a Frame Alternative during design. Also, some specific states can map as a modal or dialog.

By introducing states for the node, it's possible to connect a slot to the Entry Slot of any state. To say, we have a slot called toggle favorite and a favorite state of the node. You can connect a "Toggle favorite" slot with the entry node of a "favorite" state.

If you have multiple states activated on the frame, the tool will generate the final output using the top state (Something like CSS, adopt the latest one).

## Connection

A connection is a line that connects multiple slots of multiple nodes.

### Properties

- ID *
- Name
- Description
- Transition
  - Forward Transition
  - Backward Transition
- Type *
  - One direction
  - Path
    - Type
      - Invisible
      - Interactive (Modal sheet, dialog, etc.)
    - *[Target Slots]*
      - Subpath name * (Visible in the nodes map editor)
      - Display name (A localization key is required)
      - Slot ID *
- Start slot *

## Transition

A transition is a special kind of node that describes the transition behavior between two nodes. We can attach it to a **connection**, which means you can reuse the same transition across multiple connections.

## Nodes Group

Nodes could form a single group. Automatically expose slots that are not connected yet when creating a group from nodes.

During design progress, each node needs to map as a single frame. And each slot needs to map to an interactive element on the frame.

### Properties

- ID *
- Parent Group ID
- Name *
- Description
- *[Child Groups]*
  - Group ID
- *[Child Nodes]*
  - Node ID
