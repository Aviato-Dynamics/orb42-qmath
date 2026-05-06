# orb42-qmath

Pure C99 Q4.28 fixed-point math library — portable, zero dependencies, made for **GBA / Pokémon ROM hacking / low-power FM synthesis**.

- Range: -8.0 … +7.999999999
- 256-entry sine LUT + linear interpolation (super clean oscillators)
- Built-in FM operator
- Perfect-fifth harmonic generator
- No floats, no UB, no assembly

Originally written because a YouTube video claimed floats were "more accurate" for Pokémon Gen 3 catch rates. This library proves integers win.

## Quick start

```c
#include "orb42-qmath.h"

q4_28_t x = float_to_q(1.5);
q4_28_t y = q_mul(x, int_to_q(3));  // 4.5 in Q4.28
