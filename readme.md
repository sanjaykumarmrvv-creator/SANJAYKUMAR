
<div align="center">

# 🎓 Exam Timetable Scheduler

### Conflict-Free Scheduling using Graph Coloring

[![Made with JavaScript](https://img.shields.io/badge/Made%20with-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![DAA Project](https://img.shields.io/badge/DAA-Graph%20Coloring-6366f1?style=for-the-badge)](https://en.wikipedia.org/wiki/Graph_coloring)
[![License: MIT](https://img.shields.io/badge/License-MIT-22d3ee?style=for-the-badge)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-10b981?style=for-the-badge)](CONTRIBUTING.md)

*A web-based tool that generates conflict-free examination timetables using **Graph Coloring** heuristics.*

[Live Demo](https://your-username.github.io/exam-timetable-scheduler/) · [Report Bug](../../issues) · [Request Feature](../../issues)

</div>

---

## 📖 Overview

Educational institutions face a classic scheduling problem: **two subjects taken by the same student cannot have exams at the same time.** As the number of subjects and students grows, manual scheduling becomes impractical.

This project models the problem as a **Graph Coloring** problem and solves it using three heuristics:

| Graph Concept | Exam Scheduling |
|---------------|-----------------|
| Vertex | Subject |
| Edge | Two subjects share a student |
| Color | Time Slot |
| Chromatic Number | Minimum exam slots required |

The result is a **conflict-free timetable** that uses the **minimum number of slots**, reducing exam days for students and institutions.

---

## ✨ Features

- 🎯 **Three Coloring Algorithms** — DSATUR, Welsh–Powell, and Greedy (baseline)
- 🕸️ **Interactive Conflict Graph** — SVG visualization with hover highlighting
- 📋 **Step-by-Step Execution Log** — see exactly how each subject got its slot
- 📅 **Color-Coded Timetable** — organized by exam slot
- 📊 **Algorithm Comparison Chart** — compare slot efficiency across algorithms
- ✅ **Automatic Validity Check** — confirms zero conflicts
- ⚡ **Zero Backend** — runs entirely in the browser
- 📱 **Responsive Design** — works on desktop, tablet, and mobile

---

## 🚀 Quick Start

### Option 1 — Run Locally

```bash
git clone https://github.com/your-username/exam-timetable-scheduler.git
cd exam-timetable-scheduler
```

Simply open `index.html` in your browser. No build step, no dependencies.

### Option 2 — Live Demo

Visit: **https://your-username.github.io/exam-timetable-scheduler/**

---

## 🧠 Algorithms

### 1. DSATUR (Degree of Saturation) ★ Recommended

Selects the uncolored vertex with the **highest saturation** (number of distinctly colored neighbors), breaking ties by **degree**. Produces near-optimal colorings.

```
Saturation = |{ distinct colors among neighbors }|
```

### 2. Welsh–Powell Greedy

Sorts vertices by **descending degree**, then assigns the smallest available color to each vertex in that order.

### 3. Greedy (Input Order)

Colors vertices in the order they appear in the input — used as a **baseline** for comparison.

See [docs/ALGORITHM.md](docs/ALGORITHM.md) for detailed pseudocode and complexity analysis.

---

## 📊 Sample Results

**Input:** 9 subjects · 10 students · 18 conflict edges

| Algorithm | Slots Used | Quality |
|-----------|:----------:|:-------:|
| **DSATUR** | **4** | ★ Best |
| Welsh–Powell | 5 | Good |
| Greedy (Input) | 6 | Baseline |

> **DSATUR reduced exam slots by 33%** compared to the naive greedy approach.

---

## 🛠️ Tech Stack

- **HTML5** — semantic structure
- **CSS3** — dark glassmorphic UI, no frameworks
- **Vanilla JavaScript (ES6)** — algorithms and interactivity
- **SVG** — conflict graph rendering

No build tools. No npm. Just open and run.

---

## 📂 Project Structure

```
exam-timetable-scheduler/
├── css/
│   └── style.css              # All styling
├── js/
│   ├── constants.js           # Palette, slot labels
│   ├── parser.js              # Student–subject input parser
│   ├── graph.js               # Conflict graph builder
│   ├── algorithms.js          # DSATUR, Welsh–Powell, Greedy
│   ├── render.js              # UI rendering (graph, log, timetable)
│   └── main.js                # Entry point and event handlers
├── docs/
│   ├── ALGORITHM.md           # Detailed algorithm explanation
│   └── SETUP.md               # Local development guide
├── index.html                 # Main entry point
├── LICENSE
├── CONTRIBUTING.md
└── README.md
```

---

## 🧪 Input Format

One student per line, in the format `Name: Subject1, Subject2, ...`

```
Aarav: Data Structures, Algorithms, DBMS, Operating Systems
Diya: Algorithms, DBMS, Computer Networks
Kabir: Data Structures, Operating Systems, Machine Learning
```

Two subjects taken by the same student automatically get a **conflict edge** between them.

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) to get started.

1. Fork the repository
2. Create a branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgements

- **DAA Course Faculty** — for the problem inspiration
- **Welsh & Powell (1967)** — foundational greedy coloring heuristic
- **Brélaz (1979)** — DSATUR algorithm
- **Hackathon Organizers** — for the opportunity

---

<div align="center">

**⭐ Star this repo if you found it useful!**

Made with 💙 for the DAA Hackathon

</div>