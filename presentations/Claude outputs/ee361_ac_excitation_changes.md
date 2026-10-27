# ee361_ac_excitation.html: proposed changes

Each change is numbered so you can reply with something like "apply 1–10, skip 15". Nothing has been changed in your deck yet.

Two new interactives are saved in `interactive/`:

- `ac_excitation_explorer.html`: V, f, N → B(t) → i(t). Linear / Saturating / Hysteresis iron, B–H trace, current harmonics, core loss, 7 quiz questions. URL options: `?embed`, `V=`, `f=`, `N=`, `model=lin|sat|hys`, `play=0`.
- `coupled_coils_explorer.html`: L₁, L₂, k, i₁, i₂, separate / series aiding / series opposing, mutual and leakage flux, energy terms, 6 quiz questions. URL options: `?embed`, `L1=`, `L2=`, `k=`, `i1=`, `i2=`, `conn=sep|aid|opp`.

The review copy is `Claude outputs/ee361_ac_excitation_proposed.html`.

---

## A. Corrections

**1. Use ℛ for reluctance** (slides *In linear systems…* and *Inductance: L = N²/R*). Plain R reads as resistance; the magnetic circuits deck uses ℛ.

```
### In linear systems (e.g. air-cored inductor):

## \\( L =   \dfrac{d \lambda}{d I} =N \dfrac{\Phi}{I}\\)
--

## \\( \Phi =   \dfrac{ N I}{\mathcal{R}} \\)
--

## \\( L =  N \dfrac{\Phi}{I} = N \dfrac{N I }{I \mathcal{R}} =  \dfrac{N^2 }{\mathcal{R}}\\)
---
# Inductance


## \\( L =   \dfrac{N^2}{\mathcal{R}} = \dfrac{N^2 \mu A }{l}\\)

## Inductance increases with the square of number of turns \\(N^2\\)!
```

**2. Inductance definition: add one line linking to saturation** (slide *Inductance is the flux linkage created per ampere*). Sets up the later "inductance gets lower" slide.

```
### In a linear core this is simply \\( L = \lambda / I \\). If the core saturates, the slope \\( d\lambda / dI \\) drops.
```

**3. AC Excitation: `w` → `\omega`**

```
## \\(\Phi(t) = \Phi_{max} \sin (\omega t)\\)
```

**4. Twisted pair: fix grammar and the explanation**

```
### Twisting minimizes the mutual inductance to nearby noise sources: the voltages induced in neighbouring loops cancel, so the net flux linkage is close to zero.
```

**5. Saturation slide: "get" → "gets", and say why**

```
### If the core saturates, the inductance gets lower: \\( L = d\lambda/di \\) is the slope of the curve.
```

**6. Stored energy: `L_11`, `L_22` → `L_1`, `L_2`**, to match the mutual-inductance and series slides.

```
## \\(= \dfrac{1}{2} L\_{1}i\_1^2 + \dfrac{1}{2} L\_{2}i\_2^2 +  M i\_1 i\_2\\)
--

### In the matrix form

### \\(W\_{mag}=\dfrac{1}{2}  \begin{bmatrix}  i\_1 & i\_2  \end{bmatrix} \begin{bmatrix}  L\_{1} & M \\\ M & L\_{2} \end{bmatrix} \begin{bmatrix}  i\_1 \\\ i\_2  \end{bmatrix}\\)
```

---

## B. New slides

**7. Try it: L ∝ N²** (after *Inductance: L = N²/ℛ*). Reuses the Magnetic Circuit Explorer at N = 10 with the 3 mm gap (L ≈ 101 µH). Students double N and see 4× L.

```
---
# Try it: Double the turns

<iframe src="interactive/magnetic_circuit_explorer.html?embed&N=10&g=3" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/magnetic_circuit_explorer.html](https://keysan.me/presentations/interactive/magnetic_circuit_explorer.html)
```

**8. Coupling coefficient** (after *Mutual Inductance: V₂ = M dI₁/dt*). The deck uses M but never says how big it can be; series and energy slides need it.

```
---
# Coupling Coefficient

## Not all flux of coil 1 links coil 2 (leakage flux)
--

## \\( M = k \sqrt{L\_1 L\_2} \qquad 0 \le k \le 1 \\)
--

### k ≈ 1: coils on a shared iron core (transformers)
### k ≪ 1: air-cored coils far apart
--

### On a shared core with no leakage: \\( M = \dfrac{N\_1 N\_2}{\mathcal{R}} \\)
```

**9. Series connected coupled coils** (after *What is the equivalent inductance if two inductors are connected in series?*). Gives the answer the question slide promises. Replaces the empty *Example* slide (see 18).

```
---
# Series Connected Coupled Coils

### Same current through both coils. The dots show the winding direction.
--

## Series aiding: \\( L\_{eq} = L\_1 + L\_2 + 2M \\)
--

## Series opposing: \\( L\_{eq} = L\_1 + L\_2 - 2M \\)
--

### Measure both and find \\( M = \dfrac{L\_{aid} - L\_{opp}}{4} \\)
```

**10. Try it: Coupled coils** (after 9). Opens in series aiding at k = 0.8. Ask: set k = 1, then switch to opposing (L_eq → 0, bifilar winding).

```
---
# Try it: Series Aiding vs. Opposing

<iframe src="interactive/coupled_coils_explorer.html?embed&conn=aid&k=0.8" width="800" height="420" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/coupled_coils_explorer.html](https://keysan.me/presentations/interactive/coupled_coils_explorer.html)
```

**11. Try it: Stored energy** (after the *Stored Energy* slide). Opens with i₂ = −i₁: the mutual term is negative but W stays positive.

```
---
# Try it: Can the Mutual Term be Negative?

<iframe src="interactive/coupled_coils_explorer.html?embed&conn=sep&k=0.6&i1=5&i2=-5" width="800" height="420" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/coupled_coils_explorer.html](https://keysan.me/presentations/interactive/coupled_coils_explorer.html)
```

**12. Voltage sets the flux** (after *AC Excitation: Φ(t)…* with the linear-material figure). This is the main result of AC excitation and is missing from the deck. You will need 4.44 f N A B again in the transformer lectures.

```
---
# Voltage Sets the Flux

## \\( v(t) = N \dfrac{d\Phi}{dt} = N \omega \Phi\_{max} \cos(\omega t) \\)
--

## \\( V\_{rms} = \dfrac{2 \pi}{\sqrt{2}} f N \Phi\_{max} = 4.44 \, f N A B\_{max} \\)
--

### The supply (V and f) fixes the flux. The current is whatever the core needs to create that flux.
--

### Example: 230 V, 50 Hz, N = 300, A = 25 cm². What is \\(B\_{max}\\)?
```

**13. Try it: AC excitation** (after the *AC Excitation Non-linear B-H material* GIF slide). Opens Linear at 230 V / 50 Hz / 300 turns (B = 1.38 T, answers 12). Then press Saturating, then "+20% voltage": î rises from 0.65 A to 3.5 A.

```
---
# Try it: Linear vs. Saturating Core

<iframe src="interactive/ac_excitation_explorer.html?embed&model=lin" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/ac_excitation_explorer.html](https://keysan.me/presentations/interactive/ac_excitation_explorer.html)
```

**14. What if the frequency drops?** (after 13). Short question slide; the "40 Hz supply" button answers it.

```
---
# What if the Frequency Drops?

## \\( B\_{max} = \dfrac{V\_{rms}}{4.44 \, f N A} \\)
--

### A 60 Hz transformer connected to a 50 Hz grid carries 20% more flux
--

### This is why AC motor drives keep V/f constant
```

**15. Excitation current** (after the last *AC Excitation* slide, replacing the commented-out block at the end). Rewritten, no EE281 link.

```
---
# Excitation Current

## \\( i\_e(t) = i\_c(t) + i\_m(t) \\)

### Core-loss component \\(i\_c\\): in phase with v, supplies hysteresis and eddy-current losses
### Magnetizing component \\(i\_m\\): 90° behind v, creates the flux
--

### Energy lost per cycle = area of the B–H loop × core volume
```

**16. Try it: Excitation current with hysteresis** (after 15). Shows i_c and i_m separately and the loop area.

```
---
# Try it: Core-loss and Magnetizing Current

<iframe src="interactive/ac_excitation_explorer.html?embed&model=hys" width="800" height="480" style="border:0"></iframe>

#### Try it yourself: [keysan.me/presentations/interactive/ac_excitation_explorer.html](https://keysan.me/presentations/interactive/ac_excitation_explorer.html)
```

---

## C. Cleanup

**17. Remove the broken `MathJax.Hub.Queue(...)` block.** Same jQuery `$` error as in the other decks.

**18. Remove the empty `# Example` slide** after *Mutual Inductance: V₂ = M dI₁/dt* (replaced by 9).

**19. Delete the two commented-out blocks**: the review at the top (Magnetic Circuits 2 covers it) and the hysteresis/phasor block at the end. The latter links to `ee281_phasor_circuit_analysis.html`, which your EE361 students haven't taken. Change 15 replaces it.

**20. Hot-linked images: worth replacing with local copies in `images/ee361/`.** I couldn't check these from here (no internet access on this side), so these are risks, not confirmed breakages:
- shutterstock `stock-photo-electronic-components…jpg`: a watermarked preview of a paid stock photo. Replace with your own photo of a planar PCB coil.
- researchgate `…Magnetization-curve…ppm`: ResearchGate blocks hot-linking often, and `.ppm` may not display.
- coilws.com, 5.imimg.com, stl.tech, smar.com.br, industrial.panasonic.com: commercial pages that move often.
- ibiblio Kuphaldt figures (02307, 02336): stable, and under the Design Science License, so you can copy them locally.
