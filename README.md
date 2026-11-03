<div align="center">

# 🧊 Rubik's Cube Solver

**An open-source, interactive 3D Rubik's Cube solver in a single, dependency-free HTML file.**

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](index.html)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](index.html)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](index.html)
[![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)](#technology-stack)
[![Build](https://img.shields.io/badge/build-none_required-success)](#getting-started)
[![Last commit](https://img.shields.io/github/last-commit/Eugene-Kar/Rubiks-Cube-Solver)](https://github.com/Eugene-Kar/Rubiks-Cube-Solver/commits)
[![Stars](https://img.shields.io/github/stars/Eugene-Kar/Rubiks-Cube-Solver?style=flat)](https://github.com/Eugene-Kar/Rubiks-Cube-Solver/stargazers)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

</div>

---

## Overview

Enter the colours of your scrambled cube, press **Solve it!**, and step through a short, animated solution on a fully 3D cube. Everything runs locally in your browser: no server, no build step, no packages.

## Features

- 🎨 **Colour entry** – paint each face of the cube from a palette, with input validation
- 🧠 **Fast optimal-ish solving** – Kociemba two-phase algorithm, typically ~20 moves or fewer
- 🎬 **Animated step-through** – click **Next ▶** to watch every move on the 3D cube
- 🖱️ **Interactive 3D view** – rotate the cube to inspect any side
- 📦 **Single file** – everything lives in [`index.html`](index.html)
- 🔒 **Private & offline** – no network requests, no tracking

## Getting Started

No installation needed.

```bash
git clone https://github.com/Eugene-Kar/Rubiks-Cube-Solver.git
cd Rubiks-Cube-Solver
# open index.html in any modern browser, or serve it:
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Usage

1. Hold the cube with **white on top** and **green in front**.
2. Enter the colours face by face: **front, right, back, left, top, bottom**.
3. Press **Solve it!**
4. Click **Next ▶** to step through the animated solution.

## Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Markup | HTML5 | Page structure and UI controls |
| Styling | CSS3 (3D transforms, `perspective`, custom properties) | Rendering and animating the cube without WebGL or canvas |
| Logic | Vanilla JavaScript (ES6+) | UI, state, validation, animation |
| Solver | Kociemba two-phase algorithm (cubie-level, IDA\* search) | Computing the solution |
| Dependencies | None | Zero libraries, frameworks, or build tooling |

## How It Works

The solver models the cube at the cubie level (corner/edge permutation and orientation), validates the input for solvability (parity, orientation sums, piece uniqueness), and then runs the **two-phase algorithm**: phase 1 reduces the cube to the subgroup ⟨U, D, R2, L2, F2, B2⟩, and phase 2 solves it within that subgroup using pruning tables and IDA\* search. The resulting move sequence is animated using CSS 3D transforms.

## Project Structure

```
.
├── index.html   # UI, 3D renderer, and solver – the entire app
├── LICENSE      # Apache License 2.0
└── README.md
```

## Contributing

Contributions are welcome! Fork the repo, create a branch, make your changes, and open a pull request. Bug reports and feature ideas can be filed as [issues](https://github.com/Eugene-Kar/Rubiks-Cube-Solver/issues).

## License

Distributed under the [Apache License 2.0](LICENSE).
