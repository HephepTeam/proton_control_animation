---
title: ProtonControlCopyAnimation
layout: default
nav_order: 2
parent: Reference
---

# ProtonControlCopyAnimation

Makes a single animation work on multiple control nodes.

This is useful to avoid duplicating the same animation setup multiple times.
Create a Copy node **as a child of the animation** you want to duplicate.

Internally, this simply duplicates the parent `ProtonControlAnimation` node as many times as there are extra targets.

**Note**: If the `trigger_source` is not set, or if the animation is started through direct event connection,
all the animation copies will be triggered by the same source.
If you want the copies to be independent, the target and trigger_source must be the same, then the copy node
will be able to automatically update the duplicates with the right source.

See `03_copies.tscn` and `04_copies_with_the_same_event_source.tscn` for examples.

## Properties

#### Extra targets

- An array of control nodes that will also be affected by the animation.
- The `ProtonControlAnimation` node is duplicated for each of these nodes.
