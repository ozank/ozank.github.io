# ee361_ac_circuits.html: proposed changes

Each change is numbered so you can reply with something like "apply 1–6, skip 9". Nothing has been changed in your folder yet.

---

## A. Corrections

**1. "Derivation" → "Differentiation", and `w` → `ω`** (slide "Remember phasors are there to make your life EASIER!")

```
## Differentiation in phasor domain?
## \\(i(t)= sin (\omega t + \phi)\\)
```

**2. Angle warning** (slide "Phasors: In polar form"). Add after the `tan⁻¹` line:

```
### Careful: \\(tan^{-1}(y/x)\\) only works for \\(x>0\\). Check the quadrant (e.g. \\(-3 - j4\\) is at \\(-126.9°\\), not \\(53.1°\\))
```

**3. State which signal leads** (slide "Phase Difference" with the image). Add:

```
## \\(\phi > 0\\): the signal leads (reaches its peak earlier)
```

**4. Reactive power wording** (slide "Active and Reactive Power", 2nd one). Replace the "Remember…" line with:

```
## Real power only dissipates in resistive components.
## Ideal L and C store energy for a quarter cycle and return it in the next: the average power is zero. Reactive power describes this back-and-forth energy exchange.
```

---

## B. New slides

**5. From rotating vector to sinusoid.** Insert before the first "#Phasors" slide:

```
---
# Where does a phasor come from?
## Euler: \\(e^{j\theta} = cos\theta + j\,sin\theta\\)
--
## \\(V\_m cos(\omega t + \phi) = Re\\{ V\_m e^{j\phi} \, e^{j\omega t}\\}\\)
--
## \\(e^{j\omega t}\\): the same rotation for every signal in the circuit, so drop it
## \\(\mathbf{V} = V\_m \angle \phi\\): only the amplitude and phase remain
```

**6. Interactive slide.** Insert after "Leading Power Factor", before the power triangle:

```
---
# Explore: Phasors, Waveforms & Power
<iframe src="interactive/ac_power_explorer.html?embed" width="860" height="560" style="border:0"></iframe>
#### Try it yourself: [keysan.me/presentations/interactive/ac_power_explorer.html](https://keysan.me/presentations/interactive/ac_power_explorer.html)
```

**7. Formulas as text.** Insert before the "Important AC Power Equations" image slide:

```
---
# Complex Power
## \\(S = V\_{rms} I\_{rms}^\* = P + jQ\\)
--
## \\(P = V I cos\theta \quad\\) (W)
## \\(Q = V I sin\theta \quad\\) (var), positive for inductive loads
## \\(|S| = V I = \sqrt{P^2 + Q^2} \quad\\) (VA)
```

**8. Worked example.** Insert after "Complex Power":

```
---
# Example
## A 230 V, 50 Hz supply feeds a series load: R = 10 Ω, L = 30 mH.
## Find: \\(Z, I, \theta\\), PF, P, Q, S
--
## \\(X\_L = 2\pi 50 \times 0.03 = 9.42\,\Omega \quad Z = 10 + j9.42 = 13.74 \angle 43.3° \,\Omega\\)
--
## \\(I = 230/13.74 = 16.74\\) A, lagging by 43.3°
--
## PF = cos(43.3°) = 0.73 lagging
--
## P = \\(I^2R\\) = 2.80 kW, Q = \\(I^2X\\) = 2.64 kvar, S = 3.85 kVA
```

**9. Why power factor matters.** Insert after the example:

```
---
# Why do we care about power factor?
## A 10 kW load on a 230 V supply:
## PF = 1.0 → I = 43.5 A
## PF = 0.8 → I = 54.3 A
--
## 25% more current → \\(1.25^2\\) = 56% more cable loss (\\(I^2R\\)), plus larger cables and transformers
--
## That's why industrial consumers pay penalties for reactive energy
--
## Solution: a parallel capacitor supplies Q locally. For the previous example, about 159 µF brings PF to 1.
```

**10. RMS of a sinusoid.** Insert after "What is RMS?" (the integral definition):

```
---
# RMS of a Sinusoid
## \\(V\_{rms} = \sqrt{\dfrac{1}{T}\int\_0^T V\_m^2 cos^2(\omega t)\, dt} = \sqrt{\dfrac{V\_m^2}{2}} = \dfrac{V\_m}{\sqrt{2}}\\)
--
## 230 V\\(\_{rms}\\) → 325 V peak
```

---

## C. Cleanup

**11. Replace the external power-factor images** (unity, lagging, leading, power triangle ×2; byjus.com and electricaltechnology.org). The interactive in #6 shows the same content live. Two options:
- (a) Keep the slides and swap the images for screenshots of the widget saved in `images/ee361/`.
- (b) Drop the three PF image slides and use the interactive slide instead.

**12. Remove the Musk/Tesla tweet slide** (or move the image into `images/ee361/`; it's hosted on a news site).

**13. Fix the broken jQuery call in the MathJax setup.** `$(...)` is undefined, so this block throws an error on load. Proposed fix: delete the `MathJax.Hub.Queue(...)` block. It only adds a CSS class that isn't used.

**14. Add the `interactive/` folder** with `ac_power_explorer.html`. After you push, it will be live on keysan.me.
