# Genetic Circuit Game (Keio-Japan 2026)

A browser game about building genetic circuits. Move a petri dish to catch falling BioBrick parts, and assemble them in the right order to complete a circuit.

## Setup

The whole game is a single HTML file, `index.html`, and it doesn't need a build step or installation. It loads [p5.js](https://p5js.org/) from a CDN, so you need an internet connection.

### Option 1: Open the file directly

1. Clone the repository:
   ```bash
   git clone https://github.com/igemkeio/genetic-circuit-game.git
   cd genetic-circuit-game
   ```
2. Open `index.html` in a modern web browser (Chrome, Firefox, Edge, Safari).

### Option 2: Run a local web server

```bash
cd genetic-circuit-game
python3 -m http.server 8000
```

Then open <http://localhost:8000> in your browser.

### Option 3: Host on GitHub Pages

The game is a static page, so you can publish it with GitHub Pages. In the repository settings, go to **Settings → Pages**, select the `main` branch and the root folder, and save.

> **Note:** The game uses a 1200 × 600 canvas. It works best on a desktop or laptop screen.

## How to Play

### Goal

Score as many points as you can in **60 seconds**.

### Controls

| Action | Control |
| --- | --- |
| Move the petri dish | Move the mouse left/right, or use the **← / →** arrow keys |
| Restart after the game ends | Click the **Play Again** button |

The dish moves only inside the central play area, between the two vertical lines.

### Parts and Points

Parts fall from the top of the screen. Catch them with your petri dish.

| Label | Part | Shape | Color | Points |
| --- | --- | --- | --- | --- |
| **P** | Promoter | Square | Red | +10 |
| **R** | RBS (Ribosome Binding Site) | Circle | Yellow | +10 |
| **G** | Gene / GFP | Capsule | Green | +30 |
| **T** | Terminator | T-shape | Blue | +10 |
| **X** | Antibiotics | Spiky | Purple | **−50** |

Avoid the antibiotics. Each one you catch costs you 50 points.

### Combo Bonus: Build a Circuit

A working gene expression circuit needs its parts in the right order:

**P (Promoter) → R (RBS) → G (Gene/GFP) → T (Terminator)**

If you catch all four parts in this order, you complete a circuit and get a **+200 bonus**. "Circuit Complete!" appears on the screen and your dish glows.

- The **Combo hint** bar at the top shows your progress. The part you need next is outlined in yellow.
- If you catch a part out of order, your combo resets. If that part is a Promoter (P), it starts a new combo.
- If you catch an Antibiotic (X), your combo resets.
- You still get each part's normal points when it breaks your combo.

### Ranking

The **TOP 3** panel on the right shows your best three scores. The game keeps them in the browser's `sessionStorage`, so they last while the tab stays open and are cleared when you close it.

## License

This project is licensed under the [MIT License](LICENSE).
