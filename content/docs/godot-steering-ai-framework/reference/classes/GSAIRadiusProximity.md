---
author: razoric
date: "2020-02-25"
description: |-
  Determines any agent that is in the specified list as being neighbors with the owner agent if
  they lie within the specified radius.
title: GSAIRadiusProximity
---

<!-- Auto-generated from JSON by GDScript docs maker. Do not edit this document directly. -->

**Extends:** [GSAIProximity](../gsaiproximity) < [Reference](../reference)

## Description ##

Determines any agent that is in the specified list as being neighbors with the owner agent if
they lie within the specified radius.

## Properties ##

Type | Name
 --- | --- 
float | radius

## Functions ##

Type | Name
 --- | --- 
int | func _find_neighbors(callback: FuncRef) -> int

## Property Descriptions ##

### radius ###

{{< highlight gdscript  >}}var radius: float{{< / highlight >}}

The radius around the owning agent to find neighbors in

## Method Descriptions ##

### \_find\_neighbors <small>(virtual)</small> ###

{{< highlight gdscript  >}}func _find_neighbors(callback: FuncRef) -> int{{< / highlight >}}

Returns a number of neighbors based on a `callback` function.

`_find_neighbors` calls `callback` for each agent in the `agents` array that lie within
the radius around the owning agent and adds one to the count if its `callback` returns true.