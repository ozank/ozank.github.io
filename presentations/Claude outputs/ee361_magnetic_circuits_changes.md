# ee361_magnetic_circuits.html + ee361_magnetic_circuits2.html: proposed changes

Each change is numbered so you can reply with something like "apply 1–3, 5, skip 4". Nothing has been changed in your decks yet.

The explorer is already saved as `interactive/magnetic_circuit_explorer.html`.

URL options: `?embed` (slide mode), `N=`, `I=`, `g=` (mm), `mur=`, `model=sat`, `play=0`.

---

## B. New slides

**1. `ee361_magnetic_circuits.html`: Try it: Reluctance of the C-core** (after the **Solutions** slide). Lets students check the reluctance exercise (with and without the gap) and see the MMF split.

```
---
# Try it: Reluctance of the C-core

<iframe src="interactive/magnetic_circuit_explorer.html?embed&g=3" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/magnetic_circuit_explorer.html](https://keysan.me/presentations/interactive/magnetic_circuit_explorer.html)
```

**2. `ee361_magnetic_circuits2.html`: Try it: Double the current** (after **What happens if you double the current?**). Starts at the exercise values (N=5, I=10 A, no gap): students read B and H, then double I.

```
---
# Try it: Double the current

<iframe src="interactive/magnetic_circuit_explorer.html?embed" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/magnetic_circuit_explorer.html](https://keysan.me/presentations/interactive/magnetic_circuit_explorer.html)
```

**3. `ee361_magnetic_circuits2.html`: Try it: Linear vs. Saturating Iron** (after **Non-Linear B-H Characteristics**). Opens in saturation (N=40, I=50 A). Switch Linear/Saturating to show the 20 T the linear model would predict.

```
---
# Try it: Linear vs. Saturating Iron

<iframe src="interactive/magnetic_circuit_explorer.html?embed&model=sat&N=40&I=50" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/magnetic_circuit_explorer.html](https://keysan.me/presentations/interactive/magnetic_circuit_explorer.html)
```

**5. `ee361_magnetic_circuits2.html`: Inductance + Try it** (before the commented-out inductance block at the end, which can then be deleted). Opens with N = 10 and the 3 mm gap (L ≈ 101 µH), so students can try the N² rule and the gap-dominated L. The quiz now has 6 inductance questions.

```
---
# Inductance

## Inductance is the flux linkage per ampere:

## \\( L = \dfrac{\lambda}{I} = \dfrac{N \Phi}{I} = \dfrac{N^2}{\mathcal{R}} \\)
--

## What happens if you double the number of turns?
--

## Inductance increases with \\(N^2\\)

---
# Try it: Inductance of the C-core

<iframe src="interactive/magnetic_circuit_explorer.html?embed&N=10&g=3" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/magnetic_circuit_explorer.html](https://keysan.me/presentations/interactive/magnetic_circuit_explorer.html)
```

---

## C. Cleanup

**4. Both decks: remove the broken `MathJax.Hub.Queue(...)` block.** It calls jQuery's `$`, which these decks don't load, so it throws an error (harmless but noisy). Same fix as in the 3-phase deck.
