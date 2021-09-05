---
author: razoric
date: "2020-02-25"
description: |-
  Calculates an acceleration that attempts to move the agent towards the center
  of mass of the agents in the area defined by the `GSAIProximity`.
title: GSAICohesion
---

<!-- Auto-generated from JSON by GDScript docs maker. Do not edit this document directly. -->

**Extends:** [GSAIGroupBehavior](../gsaigroupbehavior) < [GSAISteeringBehavior](../gsaisteeringbehavior)

## Description ##

Calculates an acceleration that attempts to move the agent towards the center
of mass of the agents in the area defined by the `GSAIProximity`.

## Functions ##

Type | Name
 --- | --- 
bool | func _report_neighbor(neighbor: GSAISteeringAgent) -> bool

## Method Descriptions ##

### \_report\_neighbor <small>(virtual)</small> ###

{{< highlight gdscript  >}}func _report_neighbor(neighbor: GSAISteeringAgent) -> bool{{< / highlight >}}

Callback for the proximity to call when finding neighbors. Adds `neighbor`'s position
to the center of mass of the group.