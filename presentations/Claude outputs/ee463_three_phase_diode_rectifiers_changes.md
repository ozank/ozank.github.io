# ee463_three_phase_diode_rectifiers.html: proposed changes

Each change is numbered so you can reply with something like "apply 1–10, skip 14". Nothing has been changed in the deck yet.

New interactive (already in your folder): `interactive/three_phase_rectifier_explorer.html`. It covers the bridge and the half-wave circuit, conducting diodes and current path at any ωt, v_Pn / v_Nn / v_d, line-to-line envelope, i_a and its spectrum, overlap with L_s, plus 6 quiz questions. URL parameters: `?embed`, `mode=half`, `Ls=2`, `Id=40`, `wt=45`, `play=1`.

---

## A. Corrections

**1. Fix the broken MathJax setup.** Same bug as the EE361 decks: `$(...)` (jQuery) isn't loaded, so the `MathJax.Hub.Queue(...)` block throws on load. Delete that block.

**2. Comparison table: the header row is broken, and the half-wave row is mislabelled.** The separator line has 5 columns for a 4-column table, and "Half Bridge" means something else in power electronics (two switches + split capacitor). Replace the slide:

```
---
# Comparison of Rectifiers
### 230 V / 400 V, 50 Hz supply, constant \\(I\_d\\) load, \\(L\_s = 0\\)

| Type | \\(V\_{d}\\) | \\(\Delta v\_{d}\\) (pk-pk) | \\(f\_{ripple}\\) | PF |
|:---:|:---:|:---:|:---:|:---:|
| **1-phase bridge** | \\(\dfrac{2\sqrt{2}}{\pi}V\_{ph}\\) = 207 V | \\(\sqrt{2} V\_{ph}\\) = 325 V | 100 Hz | 0.90 |
| **3-phase half-wave (3-pulse)** | \\(\dfrac{3\sqrt{2}}{2\pi}V\_{LL}\\) = 270 V | \\(\dfrac{\sqrt{2}}{2} V\_{ph}\\) = 163 V | 150 Hz | 0.68 |
| **3-phase bridge (6-pulse)** | \\(\dfrac{3\sqrt{2}}{\pi}V\_{LL}\\) = 540 V | \\(( 1-\frac{\sqrt{3}}{2}) \sqrt{2}V\_{LL}\\) = 75.8 V | 300 Hz | 0.955 |
```

**3. Half-wave average voltage: say which voltage.** `V_rms` is ambiguous here (phase or line?).

```
## \\(V\_{dc}= \dfrac{3\sqrt{6}}{2 \pi} V\_{ph} = \dfrac{3\sqrt{2}}{2 \pi} V\_{LL} = 0.675\,V\_{LL}\\)
### = 270 V for a 400 V grid
```

**4. Bridge average voltage: fix the stray colon.** `--` followed by `: Twice of the half wave rectifier` renders as ": Twice of…". Replace with:

```
### Twice the half-wave value (two 3-pulse groups in series, shifted by 60°)
```

**5. "No 3rd order harmonics!": make it precise.** Replace with:

```
## Only \\(h = 6k \pm 1\\): 5, 7, 11, 13 … with \\(I\_{sh} = I\_{s1}/h\\)
### No even harmonics (half-wave symmetry), no triplens (120° conduction)
```

**6. Commutation formula: escape the underscores.** `L_s I_d` (unescaped) can be eaten by remark's markdown as italics. Use `L\_s I\_d`. Also add the overlap angle (see #12).

**7. Dead simulation links.** Both MultiSim Live links now redirect to NI's product page (MultiSim Live has been discontinued). The ehu.eus PDF didn't load for me either; please check it. Replace the link line with:

```
### [Interactive: 3-phase rectifier with commutation](./interactive/three_phase_rectifier_explorer.html?Ls=2&Id=40)
```

---

## B. New slides

**8. Interactive slide: diode-by-diode walk-through.** Replace the empty "Output voltage waveforms" slide (it has a title and nothing else):

```
---
## 3-Phase Full Wave (Bridge) Rectifier
### Which diodes conduct? Press Play, or "Next step"

<iframe src="./interactive/three_phase_rectifier_explorer.html?embed" width="790" height="560" style="border:0"></iframe>

#### Try it on your phone: [keysan.me/presentations/interactive/three_phase_rectifier_explorer.html](https://keysan.me/presentations/interactive/three_phase_rectifier_explorer.html)
```

**9. Quick question** (before #8, after "Ignore Ls and redraw"):

```
---
# Quick Question
### At \\(\omega t = 45^∘\\): \\(v\_{an}\\) is the most positive, \\(v\_{bn}\\) the most negative
## Which diodes conduct? What is \\(v\_d\\)?
--

## \\(D\_1\\) (top group picks the highest anode) and \\(D\_6\\) (bottom group picks the lowest cathode)
## \\(v\_d = v\_{an} - v\_{bn} = v\_{ab}\\): always the largest line-to-line voltage
```

**10. Why nobody uses the half-wave circuit** (after the half-wave average voltage slide):

```
---
## 3-Phase Half Wave Rectifier: the catch
--
### Each phase current is a one-way 120° pulse: average \\(I\_d/3\\)
## DC current in every transformer winding → core saturation
--
### The neutral carries the full \\(I\_d\\)
--
### Ripple: 163 V pk-pk at 150 Hz (bridge: 75.8 V at 300 Hz)

#### [Try it: half-wave mode](./interactive/three_phase_rectifier_explorer.html?mode=half)
```

**11. Input current and power factor** (after the current-waveform slides):

```
---
## Input Current: How Good Is It?
### \\(i\_a = \pm I\_d\\) for 120°, zero for 60°
--
## \\(I\_{s1} = \dfrac{\sqrt{6}}{\pi} I\_d = 0.78\, I\_d \qquad I\_s = \sqrt{\dfrac{2}{3}}\, I\_d = 0.816\, I\_d\\)
--
## THD = 31 % (1-phase bridge: 48 %)
--
## DPF = 1, \\(PF = \dfrac{I\_{s1}}{I\_s} DPF = \dfrac{3}{\pi} = 0.955\\)
```

**12. Overlap angle + worked example** (after "Average Voltage: With Commutation"):

```
---
# Commutation: Overlap Angle
### Two phases conduct together; the terminal sits at their average
## \\(\cos u = 1 - \dfrac{2\omega L\_s I\_d}{\sqrt{2}\,V\_{LL}}\\)
--

### Example: 400 V, \\(L\_s\\) = 2 mH, \\(I\_d\\) = 40 A
### \\(\omega L\_s = 0.628\,\Omega\\), \\(\cos u = 0.911\\) → \\(u = 24.3^∘\\)
### \\(\Delta V\_d = \dfrac{3}{\pi}\omega L\_s I\_d = 24\\) V → \\(V\_d = 516\\) V
--

### Like a DC source with internal resistance \\(3\omega L\_s/\pi\\) (lossless!)

---
## Commutation: see it

<iframe src="./interactive/three_phase_rectifier_explorer.html?embed&Ls=2&Id=40&wt=42" width="790" height="560" style="border:0"></iframe>
```

**13. Diode ratings** (before the comparison table):

```
---
## Diode Ratings (Bridge)
### Each diode conducts for 120°
## \\(I\_{D,avg} = I\_d/3 \qquad I\_{D,rms} = I\_d/\sqrt3\\)
--
## Peak reverse voltage = \\(\sqrt2 V\_{LL}\\) = 566 V for a 400 V grid
### (same for the half-wave circuit). With margin: 1200 V diodes
```

---

## C. Cleanup

**14. Remove the blogspot bridge-diagram slide.** It's a hotlinked image (`2.bp.blogspot.com`) and the next slide already shows the same circuit from your own `images/ee463/3ph_full_bridge.png`.

**15. Remove the empty "Output voltage waveforms" slide** (replaced by #8).

**16. `http://` → `https://`** for keysan.me links (mixed content on the https site).
