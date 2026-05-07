# orb42-qmath

Pure C99 **Q4.28 fixed-point math library** — portable, deterministic, and zero-dependency.  
Designed for **GBA homebrew, Pokémon Gen 3 mechanics, emulator accuracy, and low-power FM synthesis**.

- Range: **−8.0 … +7.999999999**
- 256-entry sine LUT + linear interpolation (clean, stable oscillators)
- Built-in **FM operator** (phase-accurate, drift-honest)
- **Perfect-fifth harmonic generator**
- No floats, no UB, no architecture quirks
- Header-only, drop-in, works everywhere

Originally written because a YouTube video claimed floats were “more accurate” for Pokémon Gen 3 catch rates.  
This library exists to demonstrate the opposite: **deterministic fixed-point beats floats every time**.

---

## Quick start

```c
#include "orb42-qmath.h"

q4_28_t x = float_to_q(1.5);
q4_28_t y = q_mul(x, int_to_q(3));  // 4.5 in Q4.28
```

---

## Why Q4.28?

Many retro systems — including the GBA — rely on fixed-point math for:

- deterministic game logic
- reproducible RNG behaviour
- accurate physics
- FM synthesis
- cross-platform consistency

Floating-point introduces platform-dependent drift, rounding differences, and desyncs.  
Q4.28 gives you:

- predictable behaviour  
- bit-exact results  
- portable DSP  
- clean oscillators  
- safe FM stepping  

Perfect for ROM hacks, emulators, and embedded audio.

---

## Features

### ✔ Fixed-point core
- Q4.28 format  
- add/sub/mul/div  
- safe saturating behaviour  
- integer + float conversions  

### ✔ Trigonometry
- 256-entry sine LUT  
- linear interpolation  
- cosine via quarter-turn offset  
- stable across all platforms  

### ✔ FM operator
- phase accumulator  
- modulation input  
- deterministic stepping  
- ideal for chiptune/FM synth work  

### ✔ Perfect-fifth harmonics
- generate 3:2 harmonic ratios  
- musically meaningful  
- useful for FM, envelopes, and retro audio  

---

## License

MIT — use it anywhere.
