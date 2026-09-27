# DSA Visualizer

A small, dependency-free visualizer for classic data structures & algorithms, inspired by [Algorithms-Visualizer](https://tpspace.github.io/Algorithms-Visualizer/). Built as a single `index.html` — no build step, no frameworks.

**[Live demo →](#)** *(add your GitHub Pages link here after deploying)*

## What's inside

- **Sorting** — Bubble Sort, Selection Sort, Insertion Sort, Quick Sort, animated bar-by-bar with live comparison/swap counts.
- **Binary Search** — step through a sorted array narrowing in on a target value.
- **Graph traversal** — BFS and DFS pathfinding on a clickable grid (add walls, run, watch the shortest/explored path animate).

## Running it

Just open `index.html` in a browser — or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. In the repo settings, go to **Pages** → set source to the `main` branch, root folder.
3. Your visualizer will be live at `https://<username>.github.io/<repo-name>/`.

## Project structure

```
.
├── index.html   # the whole app: markup, styles, and logic
├── README.md
└── LICENSE
```

## Extending it

Each algorithm is a small generator function (`bubbleGen`, `bfsGen`, etc.) that `yield`s a snapshot of state after each meaningful step. To add a new algorithm:

1. Write an (async) generator that yields `{ ...state }` after each step.
2. Register it (e.g. add it to the `gens` map for sorting, or a new `<option>` + branch for graph algorithms).
3. Reuse the existing render function for that panel.

Ideas for next algorithms: Merge Sort, Heap Sort, Dijkstra's, A*, linked-list operations, or a binary search tree visualizer.

## License

MIT — see [LICENSE](LICENSE).
