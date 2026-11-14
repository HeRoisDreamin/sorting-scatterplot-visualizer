<div align="center">

# 📊 Sorting Scatter Plot Visualizer

**An interactive, zero-dependency sorting algorithm visualizer powered by HTML5 Canvas, ES6 Generators, and the Web Audio API.**

![HTML5](https://img.shields.io/badge/HTML5-Canvas-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6%20Generators-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-8A2BE2?style=for-the-badge)
![Dependencies](https://img.shields.io/badge/Dependencies-Zero-3FB950?style=for-the-badge)

[**Live Demo**](https://HeRoisDreamin.github.io/sorting-scatter-visualizer/) · [**Report Bug**](https://github.com/HeRoisDreamin/sorting-scatter-visualizer/issues) · [**Request Feature**](https://github.com/HeRoisDreamin/sorting-scatter-visualizer/issues)

</div>

---

## 🎥 Preview

> *Tip: Replace this section with a screenshot or short GIF (`preview.gif`) of Quick Sort or LSD Radix Sort finishing with the RGB shimmer.*

```text
Element Value (Low → High)
  ▲
  │                         ● (Purple = High)
  │                    ●
  │               ●
  │          ●
  │     ●
  │● (Red = Low)
  └──────────────────────────▶ Array Index (0 → N - 1)
```

---

## ✨ Highlights

* **16 Sorting Algorithms:** Includes hybrid production sorts (`Introsort`), tree-based sorts (`Heap`, `BST`, `AVL`, `Tournament`), sub-quadratic networks (`Shell`, `Bitonic`), non-comparative buckets (`LSD Radix Base-8`), $O(n^2)$ classics, and meme sorts (`Stalin`, `Bogo`).
* **Beginner-Friendly Visuals:** Labeled X/Y axes, endpoint ticks (`0` to `N - 1`), a dashed diagonal target guide, and a Low-to-High HSL color bar.
* **Prismatic RGB Completion Shimmer:** Once sorted, a luminous rainbow wavefront sweeps across the diagonal (`~1.75s`) to verify monotonic order.
* **Real-Time Web Audio Synthesis:** Toggleable audio maps element values to frequencies (`180 Hz – 1000 Hz`), ending with an ascending harmonic glissando and a soft two-note chime.
* **Single-File Architecture:** Zero build steps, zero external libraries — works offline out of the box and deploys directly to GitHub Pages.

---

## 🧭 How to Read the Scatter Plot

| Visual Cue | Meaning |
| :--- | :--- |
| **X-Axis (Horizontal)** | `Array Index (0 → N - 1)` — current position in the array (left = start, right = end). |
| **Y-Axis & Dot Hue** | `Element Value (Low → High)` — mapped from **red (`0°`)** at the bottom to **purple (`280°`)** at the top. |
| **White Flashing Dots** | Elements actively being compared, shifted, or swapped. |
| **Sorted State** | Standard sorts never mutate element values (vertical height); they permute horizontal positions until all dots form a clean bottom-left to top-right diagonal. |

---

## 🧠 Supported Algorithms

| Category | Algorithm | Time (Average) | Time (Worst) | Space |
| :--- | :--- | :---: | :---: | :---: |
| **Hybrid & $O(n \log n)$** | **Introsort (`std::sort`)** | $O(n \log n)$ | $O(n \log n)$ | $O(\log n)$ |
| | **Quick Sort** | $O(n \log n)$ | $O(n^2)$ | $O(\log n)$ |
| | **Merge Sort (Bottom-Up)** | $O(n \log n)$ | $O(n \log n)$ | $O(n)$ |
| | **Shell Sort** | $O(n \log^2 n)$ | $O(n^2)$ | $O(1)$ |
| | **Bitonic Sort** | $O(n \log^2 n)$ | $O(n \log^2 n)$ | $O(1)$ |
| | **LSD Radix Sort (Base 8)** | $O(n)$ | $O(n)$ | $O(n + b)$ |
| **Tree-Based** | **Heap Sort** | $O(n \log n)$ | $O(n \log n)$ | $O(1)$ |
| | **Tree Sort (BST)** | $O(n \log n)$ | $O(n^2)$ | $O(n)$ |
| | **AVL Tree Sort (Balanced)** | $O(n \log n)$ | $O(n \log n)$ | $O(n)$ |
| | **Tournament Sort** | $O(n \log n)$ | $O(n \log n)$ | $O(n)$ |
| **$O(n^2)$ Elementary** | **Bubble Sort** | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| | **Selection Sort** | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| | **Insertion Sort** | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| | **Cocktail Shaker Sort** | $O(n^2)$ | $O(n^2)$ | $O(1)$ |
| **Meme Sorts** | **Stalin Sort** | $O(n)$ *(drops out-of-order items)* | $O(n)$ | $O(1)$ |
| | **Bogo Sort** | $O((n + 1)!)$ | Unbounded | $O(1)$ |

---

## 📁 Repository Structure

```text
sorting-scatter-visualizer/
├── index.html      # Complete standalone visualizer (HTML + CSS + JS)
└── README.md       # Project documentation
```

---

## 🚀 Quick Start

No setup or installation needed — **just left-click the [GitHub Pages link](https://HeRoisDreamin.github.io/sorting-scatter-visualizer/) and watch** the algorithms sort in real time (or download `index.html` and open it locally in any browser).

---

## ⚙️ How It Works Under the Hood

1. **ES6 Generator State Machines (`function*`):** Every sorting algorithm is written as a clean generator that `yield`s active indices on each comparison or write, decoupling algorithm logic from the 60fps `requestAnimationFrame` loop without storing memory-heavy swap histories.
2. **Power-of-Two Array Sizes ($N \in \{64, 128, 256, 512\}$):** Ensures Bitonic Sort's XOR-based sorting network (`i ^ j`) runs cleanly and allows Base-8 LSD Radix Sort to resolve $N = 512$ ($8^3$) in three crisp visual passes.

---

## 🙌 Credits & Acknowledgments

* Inspired by Timo Bingmann's [*The Sound of Sorting*](https://panthema.net/2013/sound-of-sorting/) and classic HSL scatter-plot sorting animations.
* **Built via iterative prompting by me using Gemini (`"4 hydrogen"`, `"high"` thinking level).**
