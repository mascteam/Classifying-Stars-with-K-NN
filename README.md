# Neighbours in the Night Sky — Teaching a Computer to Sort the Stars

**Subtitle:** AIML × Astrophysics, Maths & Applied Sciences Club · First-Year Interactive Session  
**Deliverable Format:** Self-contained single-file web application (`index.html`, vanilla HTML5 / CSS3 / ES6 JavaScript)

**Neighbours in the Night Sky** is a long-form, scrolling interactive lecture page designed for first-year university students with no prior background in physics or machine learning. It bridges observational astrophysics (blackbody radiation, spectral classification, absorption lines, stellar radii, and the Hertzsprung–Russell diagram) with geometric machine learning (feature spaces, non-linear decision boundaries, distance metrics, K-Nearest Neighbours, overfitting vs. underfitting, and `scikit-learn` implementation).

## Quick Start

Because the entire interactive lecture—including styles, scripts, seeded synthetic datasets, and the 240-star catalogue—is bundled inside `index.html`, no build step, bundler, or local server is required:

1. Download `index.html` to any computer, tablet, or phone.
2. Open `index.html` directly in any modern browser (Chrome, Firefox, Edge, Safari).
3. An internet connection is optional and used only to fetch the web fonts (**Bricolage Grotesque**, **Source Serif 4**, and **Fira Code** from Google Fonts) and **KaTeX 0.16.9** (`cdn.jsdelivr.net`) for rendering mathematical formulas inside collapsed *"For the curious"* boxes. Offline fallback font stacks are built in.

## Lecture Architecture (14 Numbered Blocks)

Every block follows a consistent pedagogical rhythm: **Real life analogy → Core concept (plain words first, technical term glossed) → Interactive tool → Remember takeaway**, accompanied by collapsible **Check yourself** self-tests and **For the curious** mathematical deep-dives.

| Part | Block | Title | Core Concept & Interactive Tool |
| :--- | :--- | :--- | :--- |
| **Part 1 · The Stars** (`--ember`) | **01** | What is a star? | Nuclear fusion, gravity, and why distant stars appear as dots of varying colour and brightness. *(Inline SVG diagram)* |
| **Part 1 · The Stars** (`--ember`) | **02** | Hot things glow | Blackbody radiation, Wien's displacement law, and why stars peaking in green wavelengths look warm white. (**Tool 1A**) |
| **Part 1 · The Stars** (`--ember`) | **03** | Star colours & classes | The **O B A F G K M** temperature sequence and `0–9` subclasses (the Sun at 5,772 K is `G2`). (**Tool 1B**, synced with Block 2) |
| **Part 1 · The Stars** (`--ember`) | **04** | Barcodes in starlight *(Optional)* | Quantised electron energy levels, continuous vs. absorption spectra, and element line matching. (**Tool 2**) |
| **Part 1 · The Stars** (`--ember`) | **05** | Bright because big, or because hot? | Intrinsic luminosity ($L \propto R^2 T^4$) comparing the Sun, Betelgeuse, and Sirius B. (**Tool 3**) |
| **Part 1 · The Stars** (`--ember`) | **06** | The HR diagram | Plotting absolute magnitude ($M_v$) against inverted log temperature ($\log_{10} T$) across 240 real stars. (**Tool 4**) |
| **Part 2 · The Machine** (`--indigo`) | **07** | What are AI and ML? | Rule-based programming vs. learning from examples; supervised vs. unsupervised learning comparison table. |
| **Part 2 · The Machine** (`--indigo`) | **08** | Data has a shape | Features as coordinate axes and samples as points in 2D/3D space; bands, rings, and islands vs. linear splits. (**Tools 5A & 5B**) |
| **Part 2 · The Machine** (`--indigo`) | **09** | How close is "close"? | Euclidean ($L_2$), Manhattan ($L_1$), and Chebyshev ($L_\infty$) metrics and equidistant neighbourhood shapes. (**Tool 6**) |
| **Part 2 · The Machine** (`--indigo`) | **10** | K-NN: ask your neighbours | Majority voting among $K$ nearest neighbours and how $K$ controls decision-boundary smoothness. (**Tool 7**) |
| **Part 2 · The Machine** (`--indigo`) | **11** | How is K decided? *(Optional)* | Overfitting at $K=1$ (memorising noise) vs. underfitting at $K=49$ (blurring structure) on a 70/30 split. (**Tool 8**) |
| **Part 3 · Together** (`--plum`) | **12** | Classifying a mystery star | Live K-NN classification on the 240-star HR diagram using standardised z-scores. (**Tool 9 Finale**) |
| **Part 3 · Together** (`--plum`) | **13** | Code it yourself | 4-cell interactive Python notebook covering `seaborn` HR plotting and `scikit-learn` K-NN evaluation. (**Tool 10**) |
| **Part 3 · Together** (`--plum`) | **14** | Recap and take-home | 14-block synthesis table and daily-life machine-learning reflection prompt. |

## Interactive Tools Inventory (11 Hand-Built Tools)

1. **Tool 1A & 1B · Colour and Class Explorer (Blocks 2 & 3):** Log-scale temperature slider (`2,500 K – 40,000 K`), normalised Planck spectrum curve (`50 nm – 2,500 nm`), visible rainbow strip (`380 nm – 750 nm`), Wien peak marker, live blackbody sRGB swatch, **O B A F G K M** class badge with `0–9` subclass calculation, and a three-bar Red/Green/Blue share breakdown explaining why green-peaking stars (`5,100 K – 5,900 K`) appear warm white.
2. **Tool 2 · Spectrum Barcode Explorer (Block 4):** Interactive laboratory emission strip and stellar absorption rainbow (`380 nm – 750 nm`) using accurate atomic wavelengths for Hydrogen ($\text{H}$), Helium ($\text{He}$), Sodium ($\text{Na}$), Calcium ($\text{Ca}$), Iron ($\text{Fe}$), and Magnesium ($\text{Mg}$), paired with 3 mystery stars and a multi-checkbox verification challenge.
3. **Tool 3 · Size vs. Temperature Explorer (Block 5):** Log-scale radius slider (`0.01 – 1,000` $R_\odot$) and temperature slider (`2,500 – 40,000 K`), glowing blackbody star disc next to a fixed Sun reference, and live Stefan–Boltzmann luminosity readout with presets for the **Sun** ($1\,R_\odot, 5{,}772\text{ K} \rightarrow 1.00\,L_\odot$), **Betelgeuse** ($\approx 760\,R_\odot, 3{,}600\text{ K} \rightarrow \approx 8.7 \times 10^4\,L_\odot$), and **Sirius B** ($\approx 0.008\,R_\odot, 25{,}000\text{ K} \rightarrow \approx 0.022\,L_\odot$).
4. **Tool 4 · Build the HR Diagram (Block 6):** Interactive scatter plot of the embedded 240-star dataset with inverted log temperature on the x-axis (`40,000 K` down to `2,500 K`) and inverted absolute magnitude ($M_v$) on the y-axis, distinct colour + marker shapes for all 6 stellar families, convex group hulls toggle, type filter legend, and hover/tap star inspection.
5. **Tool 5A · What is Data Space? (Block 8):** 24-row seeded fruit dataset (`Weight`, `Sweetness`, `Crunchiness`) with a 2D scatter view, a custom perspective-projected 3D rotatable cube (drag with mouse, touch, or pen), and a synchronized table that highlights the clicked point's row.
6. **Tool 5B · Bands, Rings, Islands (Block 8):** 200-point seeded datasets (`Bands`, `Rings`, `Islands (2 per colour)`, and `Separated islands`) with a two-handle draggable linear classifier showing live split accuracy alongside a one-click $K = 5$ neighbour decision-region painter with leave-one-out accuracy.
7. **Tool 6 · Distance Shapes Explorer (Block 9):** Coordinate grid with fixed point $A(0,0)$, draggable point $B$, radius slider ($r \in [1, 5]$), live path rendering and equidistant boundary shapes (circle for Euclidean, diamond for Manhattan, square for Chebyshev), and an optional $8 \times 8$ chessboard overlay displaying king-move counts.
8. **Tool 7 · Click-to-Classify K-NN (Block 10):** 60 seeded training points in two overlapping clusters where clicking or dragging moves a query point, draws lines to its $K$ nearest neighbours ($K \in \{1, 3, \dots, 15\}$), updates a live majority-vote bar, and paints 2D decision boundaries across Euclidean, Manhattan, and Chebyshev metrics.
9. **Tool 8 · How to Choose K (Block 11):** Seeded 160-point noisy two-class dataset (`mulberry32(161)`, 70/30 train/test split, ~11% flipped labels) with precomputed odd-$K$ curves from $K = 1$ to $K = 49$. Demonstrates $100.0\%$ training accuracy vs. $70.8\%$ test accuracy at $K = 1$ (overfitting), a clear test peak of $85.4\%$ at $K = 9$ ("just right"), and a drop to $45.8\%$ at $K = 49$ (underfitting).
10. **Tool 9 · Mystery Star Classifier Finale (Block 12):** Combines the 240-star HR diagram with live K-NN classification over z-score standardised features ($\log_{10} T$ and $M_v$), featuring a draggable mystery star, $K \in \{1, \dots, 15\}$ slider, metric selector, confidence bar, and presets (`Sun-like`, `Betelgeuse-like`, `Sirius B-like`, `Borderline star`).
11. **Tool 10 · Code It Yourself (Block 13):** Four all-unlocked interactive Python notebook cells with syntax highlighting, hints, kind feedback nudges, and pre-recorded outputs:
    - **Question 1 (HR Diagram Plot):** Complete `ax.invert_xaxis()` and `ax.invert_yaxis()` inside the `seaborn.scatterplot` script to render the `whitegrid` / `viridis` HR diagram.
    - **Question 2 (Step 1 — Split):** Complete `test_size=60` (or `0.25`) and `stratify=y` in `train_test_split` (`180` train / `60` test).
    - **Question 3 (Step 2 — Scale):** Complete `scaler.fit_transform(X_train)` and `scaler.transform(X_test)` using `StandardScaler`.
    - **Question 4 (Step 3 — Train, Predict & Evaluate):** Complete `KNeighborsClassifier(n_neighbors=3)`, `knn.fit(...)`, and `knn.predict(...)` to reveal the `96.67%` accuracy printout, full `classification_report`, and the $6 \times 6$ `Blues` confusion matrix heatmap.

## Embedded 240-Star Dataset (`STAR_DATA`)

The 240-row star dataset is embedded directly as a JavaScript array (`STAR_DATA`) with 40 balanced instances per class across 6 stellar types:

| Star Type ID | Stellar Family | Marker Shape | Count | Temperature Range (K) | Radius Range ($R_\odot$) | Absolute Magnitude ($M_v$) |
| :---: | :--- | :---: | :---: | :--- | :--- | :--- |
| `0` | **Brown dwarf** | Circle (`●`) | 40 | `1,939 – 3,531` | `0.057 – 0.190` | `+16.05 to +20.06` |
| `1` | **Red dwarf** | Triangle (`▲`) | 40 | `2,621 – 3,692` | `0.098 – 0.730` | `+10.12 to +14.94` |
| `2` | **White dwarf** | Diamond (`◆`) | 40 | `7,100 – 25,000` | `0.0084 – 0.015` | `+10.18 to +14.87` |
| `3` | **Main sequence** | Square (`■`) | 40 | `4,077 – 39,000` | `0.795 – 10.60` | `-4.70 to +6.51` |
| `4` | **Supergiant** | Star (`★`) | 40 | `3,008 – 40,000` | `12.0 – 98.0` | `-7.45 to -5.24` |
| `5` | **Hypergiant** | Cross (`✦`) | 40 | `3,399 – 38,940` | `708.9 – 1,948.5` | `-11.92 to -7.58` |

## Scientific & Algorithmic Implementation Details

- **Blackbody Chromaticity (`planck` & `blackbodyToSRGB`):** Integrates Planck's spectral radiance law from `380 nm` to `780 nm` (in `5 nm` steps) against the Wyman, Sloan, and Shirley (2013) piecewise-Gaussian analytic fits to the CIE 1931 $2^\circ$ colour-matching functions ($\bar{x}, \bar{y}, \bar{z}$), converts $XYZ$ to linear sRGB, normalises by the maximum positive channel to preserve chromaticity across all temperatures, clips, and applies standard sRGB gamma encoding.
- **Deterministic Reproducibility (`mulberry32`):** All synthetic point clouds (Tools 5A, 5B, 7, and 8) use seeded `mulberry32` pseudo-random number generators and Box–Muller normal sampling so every student sees the exact same data points and accuracy numbers.
- **Accessibility & Responsiveness:**
  - High-DPI (`devicePixelRatio`) canvas scaling with automatic window `resize` redrawing.
  - Unified `PointerEvent` (`pointerdown`, `pointermove`, `pointerup`) handlers supporting mouse, touch, and stylus dragging.
  - Minimum `44 px` touch targets, keyboard-accessible sliders and buttons, `aria-live="polite"` readout regions, non-colour shape encodings, `prefers-reduced-motion` compliance, and a clean `@media print` stylesheet that hides navigation rails and expands all `<details>` boxes for handouts.
