# AI Contribution Log — SLE-3 (C4 Architecture Model)

**Project:** Architectural Design (Full C4 Model) — BFS vs DFS Maze Path-Finding System
**PRN:** 25UAM108
**Name:** Prathmesh Kore
**Division:** B
**AI Tool Used:** Claude (Anthropic)

---

## 🤖 AI Contribution (Written by AI)

| # | What AI Did | Details |
|---|-------------|---------|
| 1 | Drew the Context Diagram (Level 1) | User/Operator → System → Results/Visualization, based on how the real program is actually used |
| 2 | Drew the Container Diagram (Level 2) | 5 containers derived directly from the real code's structure: Maze Input/Generator, Neighbor Provider, Search Engine, Output & Metrics, Experiment & Profiling |
| 3 | Drew the Component Diagram (Level 3) | Zoomed into the Search Engine container, matching the actual implementation: Frontier (carries (cell, path) pairs), Visited/Seen Set, Goal Test, Nodes-Expanded Counter |
| 4 | Drafted the Code Level Overview (Level 4) | Listed the real function signatures from `maze_bfs_dfs.py`: `generate_maze()`, `get_neighbors()`, `bfs()`, `dfs()`, `run_test()` |
| 5 | Drafted the Design Decisions and Conclusion text | Explained the path-in-frontier-item design choice and its memory trade-off, based on how the code actually works |
| 6 | Structured the report in the required template format | Matched the identity table, container responsibility table, and 8-section layout expected by the guideline |

---

## 🙋 My Contribution (Done by Me)

| # | What I Did | Description |
|---|-----------|-------------|
| 1 | Wrote and ran the actual BFS/DFS maze code | The `maze_bfs_dfs.py` implementation this architecture describes (from SLE-2) was written and tested independently |
| 2 | Verified every diagram box against real code | Checked that each container and component named in the diagrams corresponds to something that actually exists in my functions — not an invented or templated box |
| 3 | Rejected inapplicable template elements | Did not include a Heuristic Module (not used — no A* in this system) and did not describe a parent-map path-reconstruction step, since my actual code carries the path inside each frontier item instead |
| 4 | Filled in all identity fields | PRN, Name, Division, Date, GitHub link, System name |
| 5 | Connected this SLE back to earlier work | Confirmed the Container Diagram's "Experiment & Profiling" container accurately reflects the real py-spy profiling work completed in SLE-2 |

---

## ⚠️ Issues Found / Corrections Made

- An early draft of the Component Diagram used a "Parent Map / Path Reconstruction" box, copied from a generic C4 example — this was corrected after checking the real code, since `maze_bfs_dfs.py` does not use a parent map at all; it carries `(cell, path)` pairs directly in the frontier instead. The diagram and the accompanying text were both updated to reflect this.

---

## Summary

**AI wrote:** all three diagrams, the Code Level Overview, and the report's draft text.
**I did:** wrote and ran the real code this architecture is based on, checked every diagram box against that real code, caught and corrected one inaccurate box (the parent-map box) before accepting the diagram, and filled in all identifying details.
