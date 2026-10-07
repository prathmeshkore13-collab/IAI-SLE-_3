# SLE-3: Architectural Design (Full C4 Model)

**Course:** 02AML204 – Introduction to Artificial Intelligence
**PRN:** 25UAM108
**Name:** Prathmesh Kore
**Division:** B
**System:** BFS vs DFS Maze Path-Finding

## Objective
Converts the maze-solving system built in SLE-1 and SLE-2 into a complete
software architecture view using the C4 model — four levels of zoom, from
the whole system down to individual functions.

## System Description
The BFS vs DFS Maze Path-Finding System generates solvable grid mazes and
searches for a path from a start cell to a goal cell using either
Breadth-First Search (BFS) or depth-limited Depth-First Search (DFS). It
records path length, nodes expanded, and execution time across three maze
sizes (20x20, 40x40, 70x70), and supports CPU profiling via py-spy.

## The Four C4 Levels
1. **Context Diagram** — the system as a single box, showing how the User/Operator interacts with it and what comes out (`fig1_context.png`)
2. **Container Diagram** — 5 major building blocks: Maze Input/Generator, Neighbor Provider, Search Engine (BFS/DFS), Output & Metrics, Experiment & Profiling (`fig2_container.png`)
3. **Component Diagram** — zooms into the Search Engine: Frontier, Visited/Seen Set, Goal Test, Nodes-Expanded Counter (`fig3_component.png`)
4. **Code Level** — the actual functions: `generate_maze()`, `get_neighbors()`, `bfs()`, `dfs()`, `run_test()`

## Key Design Decision
Unlike a parent-map approach to path reconstruction, this implementation
carries the path directly inside each queued/stacked item (`(cell, path)`
pairs). This is simpler for this maze scale, at the cost of each frontier
item storing its own full path copy.

## Project Structure
```
sle3/
├── fig1_context.png      # Level 1 — Context Diagram
├── fig2_container.png    # Level 2 — Container Diagram
├── fig3_component.png    # Level 3 — Component Diagram (Search Engine)
├── SLE3_25UAM108_PrathmeshKore.docx
├── README.md
└── Contribution_Log.md
```

## How the Diagrams Were Verified
Every box in every diagram was checked against the real functions in
`maze_bfs_dfs.py` (from SLE-2) before being accepted — nothing was copied
from a generic C4 template without confirming it matched the actual code.

## AI Contribution
Claude (Anthropic) drew the three diagrams and structured this report's
template. See `Contribution_Log.md` for the full breakdown of what was
AI-generated versus independently verified.
