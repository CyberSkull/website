---
aliases:
- /docs/documentation/power-sequencer/getting-started
author: nathan
date: "2019-12-19T10:23:34+01:00"
description: Get to know Power Sequencer's core tools and workflow in this introductory
  guide.
title: Getting Started
weight: 0
---

This guide is here to get you started with Power Sequencer. It will show you time-saving features when editing with the add-on.

Power Sequencer builds upon Blender's Sequencer and adds features to help you save time when editing. It focuses on everything that has to do with cutting, trimming, moving, importing, and deleting sequences. It does not add features related to compositing or motion design.

Also, we designed it to work in conjunction with other add-ons like the [VSE Transform Tools](https://github.com/doakey3/VSE_Transform_Tools), an add-on to manipulate images directly in the sequencer preview.

## Activating the add-on ##

1. Open Blender
1. Go to `Edit > Preferences > Addons` to open the Preferences window
1. In the search box, search for "Power Sequencer"
1. Activate the checkbox next to "Sequencer: Power Sequencer"

By default, Blender will save your preferences and the add-on will be active the next time you start Blender.

## Importing your work ##

We designed Power Sequencer to work well with projects where the blend file and all the footage are in one directory:

```
.
├── 03.state-class-1.blend
└── footage
    ├── 03.state-class-1.flv
    ├── 03.state-class-2-fix-end.flv
    ├── 03.state-class-3-fix-end-2.flv
    └── BL_proxy
```

To import all the video, audio, and image files at once, go to the Power Sequencer menu and click `File -> Import Local Footage` <kbd>Ctrl</kbd> <kbd>Shift</kbd> <kbd>I</kbd>.

This feature adds strips to the editing board for each file found in your project folder. It also detects already imported footage, and only imports newly found files by default.

### Proxy preferences ###

Power Sequencer sets the strips it imports to use proxies automatically, based on your preferences:

1. Go to the Addons tab of the Preferences window
1. Search for "Power Sequencer"
1. Click the white triangle "⏴" to expand the add-on's preferences.
1. Click on the checkboxes under "Proxy" to set sequences to use these proxy sizes by default.

![Proxy preferences in the addon](img/setting-proxy-preferences.png)

## Cutting and trimming ##

A fair part of our work as editors it to make cuts in the source footage. The add-on comes with tools to save you time doing so.

### The interactive trim tool ###

Trim strips quickly by using the interactive trim tool <kbd>T</kbd>.

{{< docs-video "img/trim-interactive.mp4" "706" >}}

Tap <kbd>Shift</kbd> after entering this mode to trim all channels.

{{< docs-video "img/trim-interactive-shift.mp4" "706" >}}

### Three-point editing ###

A quick way to remove the beginning or end of strips is to use three-point editing. Move the time cursor over the strip and press <kbd>I</kbd> to remove the left portion of the strip, or <kbd>O</kbd> to remove the right.

{{< docs-video "img/trim-three-point.mp4" "706" >}}

If you want to target a single strip, hover the mouse cursor over the strip before using the hotkeys.

### Cutting audio strips ###

Showing the waveforms of audio makes cutting silence easier. To preview audio waveforms:

1. Select the audio strips on which you want to see waveforms.
2. Go to the Power Sequencer menu and click `Audio -> Toggle Waveforms` or press <kbd>Alt</kbd> <kbd>W</kbd>.

{{< docs-video "img/audio-waveforms.mp4" "706" >}}

You can then use the interactive trim tool to cut your audio visually.

### Concatenate ###

The Concatenate feature removes the gap between a selected strip and the strip to the right. Go to the Power Sequencer menu and click `Strips -> Concatenate Strips` <kbd>C</kbd>

If you want to concatenate all strips on a selected channel, press <kbd>Shift</kbd> <kbd>C</kbd>. This command removes all gaps to the right of the selected strip(s).

{{< docs-video "img/concatenate.mp4" "706" >}}

### Speeding up playback

Changing the playback speed allows for rapid previewing but also reduces the quality of the audio.

Playback speed may be set to any of the following speeds:

-  Normal (1x) <kbd>Ctrl</kbd> <kbd>1</kbd>
-  Fast (1.33x) <kbd>Ctrl</kbd> <kbd>2</kbd>
-  Faster (1.66x) <kbd>Ctrl</kbd> <kbd>3</kbd>
-  Double (2x) <kbd>Ctrl</kbd> <kbd>4</kbd>
-  Triple (3x) <kbd>Ctrl</kbd> <kbd>5</kbd>

Step through these speeds by using the period key <kbd>PERIOD</kbd> to speed up, or the comma key <kbd>COMMA</kbd> to slow down.

## Adding fades and crossfades ##

Fades help to create transitions between parts of your video. There are several options available in the Power Sequencer to add them quickly.

### Fading in and out ###

To add a fade to the start and end of strips, select them, go to the Power Sequencer menu and click `Transitions -> Fade Add` or press <kbd>F</kbd>.

{{< docs-video "img/fade-in-out.mp4" "706" >}}

To only add a fade in at the start of strips, select the strips and press <kbd>Ctrl</kbd> <kbd>F</kbd>.

To only add a fade out at the end of strips, select the strips and press <kbd>Alt</kbd> <kbd>F</kbd>.

### Editing and removing fades ###

Use the graph editor to fine-tune fades. You can replace the hovered area with the graph editor by pressing <kbd>Shift</kbd> <kbd>F6</kbd>. If you're using the [video template](https://www.gdquest.com/docs/guidelines/best-practices/making-videos/#blender-video-editing-template) this panel is open by default in the top left of the Video Editing workspace.

In the graph editor, select a node and press <kbd>G</kbd>. Use the mouse to move the node around to alter the graph.

{{< docs-video "img/fade-edit.mp4" "706" >}}

To remove any fades on a strip, click `Transitions -> Fade Clear` in the Power Sequencer menu or press <kbd>Ctrl</kbd> <kbd>Alt</kbd> <kbd>F</kbd> .

### Crossfades ###

Select the strip and go to the Power Sequencer menu. Click `Transitions -> Crossfade Add` or press <kbd>Ctrl</kbd> <kbd>Alt</kbd> <kbd>C</kbd>. This adds a crossfade between the selected strip and the strip to its right

{{< docs-video "img/crossfade-add.mp4" "706" >}}

For crossfades to work best, you should keep related strips in a single channel. Blender will add a gamma cross strip between two visual strips. It makes it easy to remove the crossfade later and prevents your editing board from getting messy.

### Editing and removing crossfades ###

To adjust the location of the crossfade between two strips, select the crossfade strip and go to `Transitions -> Crossfade Edit` in the Power Sequencer menu <kbd>G</kbd>. Drag the crossfade strip using the mouse.

{{< docs-video "img/crossfade-edit.mp4" "706" >}}

To remove a crossfade, select the crossfade strip and go to `Transitions -> Crossfade Remove`. This deletes the crossfade strip and moves the handles of the strips to form a cut again.

## Rendering your video ##

The Power Sequencer makes rendering videos as painless as possible with a few handy shortcuts.

### Render preset ###

To set the render preset to optimal settings for YouTube, go to `Apply Render Preset` in the Power Sequencer menu.

This sets the render resolution to 1080p and the video output to mp4. The video is encoded with H264, while the audio is encoded with AAC as recommended by YouTube.

### Setting the preview range ###

To easily set the preview range:

1. Select all strips by pressing <kbd>A</kbd>.
2. Go to `Preview -> Preview to Selection` or press <kbd>Ctrl</kbd> <kbd>Alt</kbd> <kbd>P</kbd>.

{{< docs-video "img/preview-to-selection.mp4" "706" >}}

### Rendering the video ###

Press <kbd>Ctrl</kbd> <kbd>F12</kbd> to start rendering the video.

Optionally, click on the `Rendering` tab near the top of the screen. This shows the rendering options on the right.

Go to the `Output` section and set the output location and name of the rendered video. By default, the video is rendered in the same location as the project's `.blend` file.
