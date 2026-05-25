# ⚔️ Triple Union Chess Matrix (v4.0 Pro)

An ambitious, high-performance tactical chess variant played on a massive 16x24 grid. The game combines **three complete sets of traditional chess pieces** lined up side-by-side, giving each team a colossal starting vanguard. It features a custom-built, threat-aware vector-matrix AI engine that executes tactical multi-move formations in real time.

<p align="center">
  <video src="gameplay.gif" width="750" autoplay loop muted playsinline></video>
</p>

---

## 🚀 Innovative Variant Mechanics

- **Multi-Action Strategic Turns:** Each team controls up to **3 individual piece movements per turn** before passing control over to the opponent.
- **Piece-Locking Regulation:** To ensure true strategic diversity, every individual piece is restricted to moving exactly **1 time per turn**. The AI cannot "double-dip" an overpowered piece to sweep a row.
- **Double-Layer Vanguard Front:** Features **48 Pawns per side** stacked in a dual-line phalanx configuration.
- **Dynamic Pawn Promotion:** Any pawn managing to successfully traverse the immense 16-rank battlefield is dynamically upgraded to a Queen upon breaching the enemy's back rank.
- **Win Condition:** The game enters a state of total structural checkmate only when **all 3 enemy Kings** have been successfully hunted down and completely eliminated from the board matrix.

---

## 📏 Custom Board Layout & Initial Thrust Rules

Traditional piece orders are multiplied by three and aligned on a 16x24 board grid. To prevent immediate bottleneck locks caused by the dense double-pawn lines, custom initialization movement rules apply:
- **Layer 1 Pawns (Ranks 1 & 14):** Permitted to execute a massive initial **3-square leap** forward if the path is clear.
- **Layer 2 Pawns (Ranks 2 & 13):** Permitted to execute an initial **2-square leap** forward.

---

## 🧠 Smart AI Engine Architecture

Unlike basic chess variants that rely on heavy object deep-copying, the **Mastermind Matrix Engine** evaluates prospective paths **in-place** using matrix arithmetic. This design avoids python memory leaks, rendering matches smoothly over hundreds of turns.

The AI's decision layer maps several core strategic principles:
1. **Threat Assessment Protocol (Anti-Suicide):** Before finalizing any movement vector, the AI scans the entire grid for enemy attack intersections. Pieces will actively refuse to blindly commit suicide on unprotected squares, protecting heavy armor assets (Queens, Rooks, Knights, Bishops) from cheap pawn trades.
2. **Phalanx Shielding Mechanics:** Pawns are specifically incentivized to move up shoulder-to-shoulder to maintain protective diagonal guard chains and robust defensive walls around active friendly Kings.
3. **King-Slayer Proximity Vectors:** The moment an enemy monarch is exposed, the engine assigns exponential value to closer squares, pulling supporting rooks and knights forward to close a trap.
4. **Stalemate Breakout Vector:** Includes a positional decay memory cache that tracks the last 6 visited coordinates per color, heavily penalizing pieces for shuffling over the same tiles repeatedly to break infinite loops.

---

## 🛠️ Architecture and Bug Fixes Implemented

This project successfully implements advanced optimization workarounds for running rich UI animations natively in cloud containers:
- **Zero-Blink HTML/JS Pipeline:** Replaced standard `matplotlib` plotting loops with an interactive `ipywidgets.HTML` template. It swaps cell-element values on a single frame, preventing the massive browser flashing typically caused by jupyter cell clearing.
- **Strict Resolution Normalization:** To prevent GIF compilation crashes (`ValueError: all input arrays must have the same shape`) when text logs word-wrapped and warped the frame dimensions, a strict scaling matrix forces every captured screenshot into a uniform **825x750 pixel box**.
- **Headless Font Rendering Integration:** Injected operating-system font bindings (`fonts-dejavu-core`) directly into the deployment loop, allowing headless background browser snapshot scripts to cleanly translate bold text chess glyphs ($♚, ♛, ♜$) inside rounded base circular elements without producing blank boxes.

---

## 🎮 How to Play

### Run instantly in the Cloud (Google Colab)
Click the blue **Open In Colab** badge at the very top of the `main.ipynb` preview file on your GitHub. Once inside the Colab workspace:
1. Select **Runtime** from the top menu bar.
2. Click **Run All** (`Ctrl + F9` or `Cmd + F9`).
3. Scroll down to the Interactive Canvas Widget and watch the high-IQ AI armies clash!
4. Check your left-hand folder sidebar once the simulation halts; your custom `gameplay.gif` will be fully compiled and ready to download!

### Run Locally on Your Computer
Ensure you have Jupyter notebook or JupyterLab installed locally alongside standard notebook interface widgets:

```bash
# Install interface rendering dependencies
pip install ipywidgets imageio imageio-ffmpeg notebook

# Launch Jupyter
jupyter notebook
