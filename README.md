# Wave-Function-Collapse

Straight out of quantum mechanics, **Wave Function Collapse** (WFC) is an algorithm for procedural generation of images. This repository features **two core approaches** to the WFC: the **Tiled Model** (Coding Challenge 171) and the **Overlapping Model** (Coding Challenge #186). Both implementations are available in JavaScript (p5.js) and ported to Processing (Java). A third, community-contributed **Hybrid Model** (`p5js/hybrid-model`) merges both approaches with automatic tile-edge detection, incremental/single-image loading, a full control UI, and performance optimizations — see [its README](p5js/hybrid-model/README.md) for the full write-up.

<img src="gifs/wfc_tiled.gif" alt="GIF animation of the tiled WFC algorithm" height="250"> <img src="gifs/wfc_overlapping.gif" alt="GIF animation of the overlapping WFC algorithm" height="250"> <img src="gifs/hybrid-wfc.gif" alt="GIF animation of the hybrid WFC algorithm" height="250">

## Coding Challenges

- [Coding Challenge #171: Wave Function Collapse](https://thecodingtrain.com/challenges/171-wave-function-collapse)
- [Coding Challenge #186: WFC Overlapping Model](https://thecodingtrain.com/challenges/186-wfc-overlapping-model) ([Available now exclusively on Nebula!](https://nebula.tv/videos/codingtrain-coding-challenge-186-wave-function-collapse))

## Archived Raw Footage

- 🔴 [Wave Function Collapse Tiled Model Live Stream #1](https://youtu.be/6Vag7NJUjJo)
- 🔴 [Wave Function Collapse Tiled Model Live Stream #2](https://youtu.be/FGmB5ZHhhiA)
- 🔴 [Wave Function Collapse Tiled Model Live Stream #3](https://youtu.be/QvoTSl60Y88)
- 🔴 [Wave Function Collapse Overlapping Model Live Stream #1](https://youtube.com/live/gwFBEUwjcGE)
- 🔴 [Wave Function Collapse Overlapping Model Live Stream #2](https://youtube.com/live/JJX_yaenzCs)

## Overview

Wave Function Collapse is a constraint-satisfaction algorithm inspired by quantum mechanics. At a high level, you have:

1. **Tiles** (or “patterns”) that can appear in each cell.
2. **Adjacency rules** describing which tiles can appear next to each other.
3. **Entropy** that helps decide which cell to collapse (choose a tile for) next.
4. **Propagation** to eliminate invalid tiles from neighbors as constraints tighten.

### Completed

- [x] Implementation of Tile Model (Challenge 171)
- [x] Implementation of Overlapping Model (Challenge 186)
- [x] Processing (Java) ports for both models
- [x] Entropy-based cell selection in the Overlapping Model (lowest-entropy cell is chosen each step, in both p5.js and Processing)
- [x] Queue-based constraint propagation with backtracking to recover from paradoxes (Overlapping Model, p5.js)
- [x] Hybrid Model: single codebase supporting both tiled and overlapping sources, with auto-detected tile-edge matching and incremental image loading (`p5js/hybrid-model`)

### Corrections / Additional Features

- [ ] Additional edge cases for tiles 4 and 5 (Tiled Model).
- [ ] Computed Property Names (Tiled Model) [Issue #35](https://github.com/CodingTrain/Wave-Function-Collapse/issues/35)

## Community Contributions and Improvements

- [TileGrid Helper Class](https://github.com/jonnytest1/Wave-Function-Collapse/tree/main) by [@jonnytest1](https://github.com/jonnytest1) A generic grid layout approach using p5.js vectors, making it easier to unify directional logic and reference valid neighboring positions.
- [Grid Update Optimization](https://github.com/gverger/Wave-Function-Collapse/tree/optim-updates): [Pull Request #40](https://github.com/CodingTrain/Wave-Function-Collapse/pull/40) introduces a more efficient method for updating grid cells by propagating changes only to affected cells, which improves performance and accuracy. The drawing process is also optimized, allowing multiple updates per tick, speeding up the overall process.
- [Using Piskel to create a source image](https://github.com/kfahn22/Wave-Function-Collapse/wiki/Creating-a-source-image-for-the-WFC-%E2%80%90-overlapping-model)
- [Highly optimized version supporting both single-image and pre-tiled source images](https://github.com/pierrebai/Wave-Function-Collapse) by [@pierrebai](https://github.com/pierrebai), merged into this repo as the **Hybrid Model** (`p5js/hybrid-model`).
  A detailed write-up of how the changes were done and why can be found in its own
  [README](p5js/hybrid-model/README.md).
- An optimized Overlapping Model using a queue (instead of recursion) and backtracking to avoid paradoxes, plus GUI improvements, by [@alin256](https://github.com/alin256) ([original branch](https://github.com/alin256/Wave-Function-Collapse/tree/efficientQueueBranch)) — merged into `p5js/overlapping-model`.


## Key Resources

- [Wave Function Collapse algorithm source](https://github.com/mxgmn/WaveFunctionCollapse)
- [Wave Function Collapse Processing forum discussion](https://discourse.processing.org/t/wave-collapse-function-algorithm-in-processing/12983)
- [Gridbugs Procedural Generation with Wave Function Collapse](https://www.gridbugs.org/wave-function-collapse/)
- [Model Synthesis by Paul Merrell](https://paulmerrell.org/model-synthesis/)
- [WFC using local storage by @kfahn22](https://editor.p5js.org/kfahn/full/iNUF-Lgdf)
