# ee361_3phase_ac.html: proposed changes

Each change is numbered so you can reply with something like "apply 1–8, skip 12". Nothing has been changed in your folder yet.

---

## A. Corrections

**1. Power Relations: add P, Q and the angle warning.** Replace the slide (also fixes `#Power` → `# Power`):

```
---
# Power Relations
--
## Regardless of the connection type (balanced load):
## \\( |S| = 3V\_{phase}I\_{phase} = \sqrt{3}V\_{LL}I\_{L}\\)
--
## \\( P = \sqrt{3}V\_{LL}I\_{L} \, cos\theta \qquad Q = \sqrt{3}V\_{LL}I\_{L} \, sin\theta\\)
--
## Careful: \\(\theta\\) is the angle of the **phase impedance** (between \\(V\_{phase}\\) and \\(I\_{phase}\\))
## It is **not** the angle between \\(V\_{LL}\\) and \\(I\_{L}\\) (that one is \\(\theta + 30^∘\\) in a Y load)
```

**2. Wye slide: add the 30° shift.** Below the two magnitude lines:

```
### \\( \vec{V\_{ab}} = \sqrt{3}\,\vec{V\_{an}} \angle 30^∘\\) (line voltage leads phase voltage by 30°)
```

**3. Delta slide: add the 30° shift.** Below the two magnitude lines:

```
### \\( \vec{I\_{a}} = \sqrt{3}\,\vec{I\_{ab}} \angle -30^∘\\) (line current lags phase current by 30°)
```

**4. Impedance Transformation: add the condition.**

```
## \\(Z_{\Delta} = 3 Z\_Y \\) (balanced loads)
```

**5. 230 V slide: replace the UK sentence.** "Due to connection of UK to European System" isn't correct: the UK isn't synchronous with the continental grid. Proposed:

```
### IEC 60038 harmonised Europe's 220 V and the UK's 240 V into a single 230 V standard
### Turkey's grid has run synchronously with the [European system (ENTSO-E)](https://www.entsoe.eu/data/map/) since 2010 (permanently since 2015)
```

**6. Voltages & Currents: state RMS or peak.** Add under the equations:

```
### \\(V\_{max}\\) is the peak value; phasors use RMS: \\(\vec{V\_{an}} = \frac{V\_{max}}{\sqrt2}\angle 0^∘\\)
```

Also make the notation consistent: `Va` → `V\_a` (and the same for b, c).

**7. "More power per unit wire length" → a more precise claim.**

```
- ## Less conductor material for the same power
### 3 single-phase circuits need 6 wires; one 3-phase circuit needs 3 (the return currents cancel)
```

**8. Fix the broken MathJax setup.** As in the AC circuits deck: `$(...)` (jQuery) isn't loaded, so this block throws an error on load. Delete the `MathJax.Hub.Queue(...)` block.

---

## B. New slides

**9. Why not 2 or 5 phases?** After the "WHY 3-PHASE?" bullets.

Correction to what I said earlier: balanced two-phase (90° apart) *also* gives constant power. The real argument for three is the conductor count.

```
---
# Why not 2 or 5 phases?
--
## 2-phase (90° apart) existed (Niagara Falls, 1895)
## Needs 4 wires, or 3 wires with a common return carrying \\(\sqrt2 I\\)
--
## 3 is the minimum number of symmetric phases whose currents sum to zero: **no return wire**
--
## More phases: more conductors, switchgear and transformer windings, for little gain
### (Multi-phase is still used inside rectifiers, ship propulsion, some EV motors)
```

**10. Balanced systems & phase sequence.** After the phasor slides:

```
---
# Balanced 3-Phase System
## \\(\vec{V\_{a}} + \vec{V\_{b}} + \vec{V\_{c}} = 0 \qquad \vec{I\_{a}} + \vec{I\_{b}} + \vec{I\_{c}} = 0\\)
--
## So the neutral current is zero → the neutral wire can be thin or omitted
--
## Phase sequence: abc (positive) or acb (negative)
### Swap any two wires → sequence reverses → a 3-phase motor turns the other way
```

**11. Per-phase analysis.** After "Impedance Transformation", before Examples:

```
---
# Per-Phase Analysis (balanced systems)
1. ## Convert any \\(\Delta\\) to an equivalent Y (\\(Z\_Y = Z\_\Delta/3\\))
2. ## Solve **phase a** only: a single-phase circuit, line-to-neutral
3. ## Phases b and c: same magnitude, shifted by \\(-120^∘\\) and \\(+120^∘\\)
4. ## Total power = 3 × phase power
```

**12. Worked example.** After per-phase analysis:

```
---
# Example
## 400 V (line-to-line), 50 Hz supply. Balanced load \\(Z = 8 + j6\,\Omega\\) per phase.
## Find \\(I\_L\\), PF, P, Q, S for Y and for \\(\Delta\\) connection
--
## **Y:** \\(V\_{ph} = 400/\sqrt3 = 231\\) V, \\(|Z| = 10\angle 36.9^∘\\), \\(I\_L = I\_{ph} = 23.1\\) A
## PF = 0.8 lagging, P = 12.8 kW, Q = 9.6 kvar, S = 16 kVA
--
## **\\(\Delta\\):** \\(V\_{ph} = 400\\) V, \\(I\_{ph} = 40\\) A, \\(I\_L = 69.3\\) A
## P = 38.4 kW, Q = 28.8 kvar, S = 48 kVA
--
## Same impedances, **3× the power** in delta (that's how Y-Δ starters work)
```

**13. Concept question.** After the example (good for a show of hands):

```
---
# Quick Question
## A balanced Y load is supplied with abc sequence. You measure that \\(V\_{ab}\\) leads \\(I\_a\\) by 60°.
## What is the power factor?
### A) 0.5 lagging    B) 0.866 lagging    C) 0.866 leading    D) Not enough information
--
## **B.** \\(V\_{ab}\\) leads \\(V\_{an}\\) by 30°, so \\(V\_{an}\\) leads \\(I\_a\\) by 30°: PF = cos 30° = 0.866 lagging
```

**14. Interactive slide: 3-Phase Explorer** (to build after you approve). Replaces the Google Sheet link and the UMN GIF links on the "WHY 3-PHASE?" slide:

```
---
## Explore: 3-Phase Waveforms, Phasors & Power
<iframe src="interactive/three_phase_explorer.html?embed" width="790" height="560" style="border:0"></iframe>
#### Try it yourself: [keysan.me/presentations/interactive/three_phase_explorer.html](https://keysan.me/presentations/interactive/three_phase_explorer.html)
```

Proposed features: waveforms + phasors with line-to-line vectors, Y/Δ toggle, load angle slider showing p_a, p_b, p_c and their constant sum, unbalance slider showing the neutral current, optional short quiz.

**20. Interactive slide: Line vs Phase explorer** (built: `interactive/line_phase_explorer.html`). Insert after the "How to measure voltage & currents?" slide with \\(\vec{V\_{ab}}= \sqrt 3 V \angle 30^∘\\):

```
---
## Where do √3 and 30° come from?
<iframe src="interactive/line_phase_explorer.html?embed" width="790" height="560" style="border:0"></iframe>
#### Try it yourself: [keysan.me/presentations/interactive/line_phase_explorer.html](https://keysan.me/presentations/interactive/line_phase_explorer.html)
```

Stationary phasors + instantaneous waveforms. 5 steps (phase voltages → flip V_bn → head-to-tail sum → 120° triangle gives √3 and 30° → all three), Y voltages / Δ currents, abc/acb, time cursor. In the slide, ↑/↓ step through the construction; ←/→ still change slides.

---

## C. Cleanup

**15. Trim the plug section (13 → 7 slides).** Proposed:
- Drop: the Schuko slide (the world-plugs slide already makes the point), the first industrial plug photo (keep the terminal identification), one of the two offshore slides, one of the two transmission line slides.
- Merge old and new colour codes into one side-by-side slide.

**16. Merge the two "How to measure voltage & currents?" image slides** (keep the GIF, or replace both with the explorer from #14).

**17. Remove links that are likely dead.** Please check in a browser (I couldn't test them from here):
- UMN animations (`people.ece.umn.edu/users/riaz/...`), replaced by #14
- UNLV "Review of three phase AC circuits" PDF
- Aurora CCS design guide PDF
- kinja offshore plug images

**18. Copy the hotlinked images into `images/ee361/`.** About 20 images come from outside sites (flixcart, smushcdn, ResearchGate, electricalvolt, emetor, inmr, medium…), and several use `http://`, which can break on the https site. I can write a small script that downloads them and rewrites the links.

**19. Consistent headers.** Use one `#` title per slide and drop the repeated "Introduction to Three Phase" headers (or keep it as a section title slide).
