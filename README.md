# 📊 Sorting Scatter Plot Visualizer

An interactive, zero-dependency sorting algorithm visualizer built with **HTML5 Canvas**, **ES6 Generators**, and the **Web Audio API** — all packed into a single self-contained HTML file.

Watch **16 sorting algorithms** untangle a shuffled rainbow scatter plot into a clean diagonal line in real time, complete with live operation counters, phase indicators, synthesized audio feedback, and a prismatic RGB verification shimmer upon completion.

---

## ✨ Features

* **16 Sorting Algorithms:** Covers hybrid production sorts, tree-based sorts, sub-quadratic networks, non-comparative radix buckets, $O(n^2)$ classics, and meme sorts.
* **Beginner-Friendly Axes & Legend:** Clearly labeled X/Y axes, endpoint ticks (`0` to `N - 1`), a subtle target diagonal guide, and a Low-to-High HSL color bar.
* **Prismatic RGB Completion Shimmer:** Once sorted, a luminous rainbow wavefront sweeps across the diagonal (`~1.75s`) to verify monotonic order.
* **Web Audio API Synthesizer:** Toggleable sound maps element values directly to frequencies (`180 Hz – 1000 Hz`), finishing with an ascending harmonic glissando and a soft two-note glass chime.
* **Zero Dependencies:** No frameworks, build tools, or external libraries — just open `visualizer.html` in any modern browser.

---

## 🧭 How to Read the Visualization

* **X-Axis (Horizontal):** `Array Index (0 → N - 1)` — where each element currently sits in the array (left = start, right = end).
* **Y-Axis (Vertical) & Color:** `Element Value (Low → High)` — the numeric value of each element, mapped from **red (`0°`)** at the bottom to **purple (`280°`)** at the top.
* **White Flashing Dots:** Elements currently being compared, shifted, or swapped.
* **Goal:** Standard sorting algorithms never change the elements' values (vertical height); they only permute their horizontal positions until every dot aligns along the bottom-left to top-right diagonal.

---

## 🧠 Included Algorithms

| Category | Algorithm | Time Complexity (Avg / Worst) | Space |
| :--- | :--- | :---: | :---: |
| **Hybrid & $O(n \log n)$** | **Introsort (`std::sort`)** | $O(n \log n)$ / $O(n \log n)$ | $O(\log n)$ |
| | **Quick Sort** | $O(n \log n)$ / $O(n^2)$ | $O(\log n)$ |
| | **Merge Sort (Bottom-Up)** | $O(n \log n)$ / $O(n \log n)$ | $O(n)$ |
| | **Shell Sort** | $O(n \log^2 n)$ / $O(n^2)$ | $O(1)$ |
| | **Bitonic Sort** | $O(n \log^2 n)$ / $O(n \log^2 n)$ | $O(1)$ |
| | **LSD Radix Sort (Base 8)** | $O(d(n + b))$ $\rightarrow O(n)$ | $O(n + b)$ |
| **Tree-Based** | **Heap Sort** | $O(n \log n)$ / $O(n \log n)$ | $O(1)$ |
| | **Tree Sort (BST)** | $O(n \log n)$ / $O(n^2)$ | $O(n)$ |
| | **AVL Tree Sort (Balanced)** | $O(n \log n)$ / $O(n \log n)$ | $O(n)$ |
| | **Tournament Sort** | $O(n \log n)$ / $O(n \log n)$ | $O(n)$ |
| **$O(n^2)$ Elementary** | **Bubble Sort** | $O(n^2)$ / $O(n^2)$ | $O(1)$ |
| | **Selection Sort** | $O(n^2)$ / $O(n^2)$ | $O(1)$ |
| | **Insertion Sort** | $O(n^2)$ / $O(n^2)$ | $O(1)$ |
| | **Cocktail Shaker Sort** | $O(n^2)$ / $O(n^2)$ | $O(1)$ |
| **Meme Sorts** | **Stalin Sort** | $O(n)$ *(eliminates out-of-order items)* | $O(1)$ |
| | **Bogo Sort** | $O((n + 1)!)$ / Unbounded | $O(1)$ |

---

## 🚀 Getting Started

1. Clone this repository or download `visualizer.html`.
2. Double-click `visualizer.html` to open it in Chrome, Firefox, Edge, or Safari.
3. Choose an **Algorithm**, pick an array size (**`N = 64, 128, 256, 512`**), adjust the **Speed** slider, and toggle **Sound** on if you want audio feedback.

---

## ⚙️ Under the Hood

* **JavaScript Generators (`function*`):** Every sorting algorithm is written as a clean, readable generator function that `yield`s active array indices on each comparison or write. This decouples algorithm execution from the 60fps `requestAnimationFrame` render loop without storing massive snapshot histories in memory.
* **Power-of-Two Array Sizes:** Using $N \in \{64, 128, 256, 512\}$ allows Bitonic Sort's XOR-based sorting network (`i ^ j`) to run cleanly and lets Base-8 LSD Radix Sort resolve $N = 512$ ($8^3$) in three crisp visual passes.

---

## 🙌 Credits

* Inspired by classic sorting visualizers (*The Sound of Sorting* by Timo Bingmann and scatter-plot sorting animations).
* **Built via iterative prompting by me using Gemini (`"4 hydrogen"`, `"high"` thinking level).**
