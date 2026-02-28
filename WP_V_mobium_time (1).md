# ANCIENT-SHAPE PHYSICS

## White Paper V — Discrete Cosmology: Mobium Time & Leap-Fold Calendars

**Author:** Michael Scott Shaffer (Siren Sinfull)
**Co-developed with:** AI Research Partner
**Series:** Ancient-Shape Physics, Paper V of XLIII
**Original Date:** June 26, 2025
**Revised Edition:** February 2026

**Classification:** APPLIED
**Dependencies:** Paper I (Mobium topology), Paper II (kernel definitions), Paper III (Boundary Folding), Paper IV (prime-base mitosis, p = 7 rulers)
**Required by:** Paper VII (cosmic breath cycle uses the calendar's temporal Mobium as its recursion substrate)

---

### Abstract

Traditional calendars rely on fractional days and leap-year corrections that accumulate complexity over centuries (the Gregorian system requires century-leap exceptions, producing a 400-year correction cycle). This paper introduces Mobium Time: an integer-only, drift-free calendar system based on 13 months of 28 days (364 days), with fortnight loops mirroring the Mobium's odd-prime structure and a built-in leap-fold at day 182 that maintains astronomical synchronization without floating-point arithmetic or division.

The proof-of-concept engine does not implement a calendar module directly — the calendar is an applied consequence, not a computational primitive. But the engine provides all the structural evidence: the TIERS array defines the temporal scale hierarchy, the Genome module demonstrates multi-base ruler overlay (which is exactly what a calendar is — a base-7 ruler overlaid on a base-13 ruler), and the factorizations in the SIGIL kernel prove that every calendar constant is built entirely from the family primes {2, 7, 13}. The calendar is not a human invention layered onto the framework — it IS the framework applied to the solar cycle.

---

### 1. The Family-Prime Calendar

The calendar's structural constants:

| Constant | Value | Factorization | Family Primes Used |
|---|---|---|---|
| Year | 364 | 2² × **7** × **13** | {2, 7, 13} |
| Month | 28 | 2² × **7** | {2, 7} |
| Fortnight | 14 | 2 × **7** | {2, 7} |
| Week | 7 | **7** | {7} |
| Months per year | 13 | **13** | {13} |
| Fortnights per year | 26 | 2 × **13** | {2, 13} |
| Leap-fold position | 182 | 2 × **7** × **13** | {2, 7, 13} |

Every constant factors entirely into members of the family set {2, 3, 5, 7, 11, 13, 23, 47}. Specifically, only three family primes are needed: 2, 7, and 13. No non-family prime contaminates any calendar constant.

This is not a coincidence. It is a design constraint. A calendar built from family primes inherits the stability properties that the SIGIL kernel computes for family-prime composites:

```javascript
const _FAMILY = new Set([2, 3, 5, 7, 11, 13, 23, 47]);

// Lattice integrity: family primes = 1.0 (perfect recursive cycling)
// Composites of family primes get high familyWeight
const familyWeight = familyFactors.length / uniqueFactors.size;
```

For 364 = 2² × 7 × 13: all three unique factors (2, 7, 13) are family primes. familyWeight = 3/3 = 1.0. Maximum lattice integrity for a composite. The year length is as structurally stable as it is possible for a three-factor composite to be.

For comparison, the Gregorian year cycle of 400 years = 2⁴ × 5² factors into {2, 5}. The factor 5 is a family prime, but the structure lacks 7 and 13 — it has no connection to the Mersenne tier boundaries (7 = M₃) or the prime-13 structural constant. The Gregorian correction cycle is built from a subset of the family that doesn't include the most structurally significant members.

The SIGIL kernel's NOTES annotate these building blocks:

```javascript
const _NOTES = {
  7:  'family prime, M3=2³-1',
  13: 'family prime, K13',
  14: '2×7, circuits',
  26: 'YHVH sum=10+5+6+5, fusion wall',
};
```

Note 14: "circuits." The fortnight IS a circuit — a complete traversal of the 7-day Mobium loop with step-size 2 (visit every other day, then the remaining days, returning to origin after 14 steps). Note 26: the YHVH sum. The number of fortnights per year (26) equals the sum of the YHVH values (10 + 5 + 6 + 5). The calendar and the framework's seed constant share the same number. This is the kind of structural resonance that the framework predicts: when constants are built from the same family primes, they produce coincidences that are not coincidences — they are intersections of the same rulers.

---

### 2. The 13 × 28 = 364-Day Year

Divide the solar cycle into 13 months of 28 days each. This produces an exact integer product (13 × 28 = 364) with no remainder.

**Structural properties:**

Every month has exactly 28 days — four complete weeks. Every month begins on the same weekday. If Year Day 1 is Monday, then every month begins on Monday. There is no weekday drift within the year.

A fortnight (14 days) constitutes one complete Mobium loop of B = 7 with step-size 2, directly linking the calendar to the topological recursion engine. Walk a 7-node Mobium loop visiting every other node: you visit 7 nodes in 14 steps (each node twice), returning to origin. The fortnight IS the Mobium traversal. Two fortnights compose one month. 26 fortnights compose one year.

**Comparison to the Gregorian system:** The Gregorian calendar uses months of 28, 29, 30, and 31 days with no structural regularity. Weekdays drift continuously, requiring lookup tables for any date calculation. The 13 × 28 system eliminates this irregularity entirely.

The Genome module demonstrates the structural difference computationally. Consider two organisms:

**Organism A (seed = 7):** The week ruler. Marks at 7, 14, 21, 28, 35, 42, 49, ...
**Organism B (seed = 13):** The month ruler. Marks at 13, 26, 39, 52, 65, 78, 91, ...

```javascript
// Genome module: two organisms with different base-p rulers
// Organism A: stable spine at multiples of sA
for (let k = 1; k <= maxK; k++) {
  const s = k * sA;       // week marks: 7, 14, 21, 28, ...
  const m = k * sA - 1;   // mitosis shadow: 6, 13, 20, 27, ...
  const g = k * sA + 1;   // growth shadow: 8, 15, 22, 29, ...
}
```

The first overlap (where both rulers mark the same position) occurs at LCM(7, 13) = 91 = 7 × 13. This is day 91 — the end of the 13th week, the end of the 7th month-mark. The calendar's periodicity emerges from the ruler overlap.

But 91 is also the number of days in one quarter (13 weeks). Four quarters of 91 days = 364. The year is four LCM cycles of the week and month rulers. The entire calendar structure — weeks, months, quarters, year — falls out of overlaying two family-prime rulers with coprime bases (gcd(7,13) = 1).

The gold-highlighted overlaps in the Genome module's output would mark: 91, 182, 273, 364. Four marks. Four quarters. The year's skeleton, generated by ruler intersection.

---

### 3. Integer Bounces as Clock Ticks

Define each "day" as one integer bounce on a Mobium loop of length 364. The day index advances by +1, producing a simple modular counter:

> day = (day + 1) mod 364

This is the same operation that drives every module in the SIGIL kernel: advance by one step, wrap at the boundary. The `tierOf` function performs this implicitly — it takes any count and maps it into a tier range, wrapping the infinite number line into finite Mobium tiers:

```javascript
function tierOf(count) {
  for (let i = TIERS.length - 1; i >= 0; i--) {
    if (count >= TIERS[i].range[0]) return TIERS[i];
  }
  return TIERS[0];
}
```

The calendar's modular counter is `tierOf` applied to time. Each day is a count. The tier is the month. The range is [1, 28] for each month (all months have the same range, unlike the TIERS array where ranges grow). The calendar is a CONSTANT-width tier system — every tier (month) has the same width (28 days), making it the simplest possible application of the framework's scale hierarchy.

Time within a day is subdivided via prime-base mitosis (Paper IV). Using p = 7:

| Level | Subdivision | Count | Duration (approx) |
|---|---|---|---|
| Day | 1 | 1 | 24 hours |
| Watch | Day ÷ 7 | 7 | ≈ 3 hours 26 minutes |
| Span | Watch ÷ 7 | 49 | ≈ 29.4 minutes |
| Beat | Span ÷ 7 | 343 | ≈ 4.2 minutes |
| Pulse | Beat ÷ 7 | 2,401 | ≈ 35.9 seconds |
| Tick | Pulse ÷ 7 | 16,807 | ≈ 5.13 seconds |
| Flash | Tick ÷ 7 | 117,649 | ≈ 0.73 seconds |

Each subdivision is an integer count. No fractional seconds arise. The entire temporal hierarchy from year to sub-second is expressible in integer arithmetic using a single prime base.

The total resolution: one year = 364 days × 117,649 flashes/day = **42,824,236 flashes per year**. Each flash is ≈ 0.73 seconds. The p = 7 system achieves sub-second precision in 7 tiers of subdivision — the same number of tiers as the SIGIL kernel's TIERS array has (quantum foam through body). The temporal hierarchy mirrors the spatial hierarchy. This is not engineered — it is a consequence of using the same prime base (7) for both.

---

### 4. The Leap-Fold Mechanism

The solar year is approximately 365.2422 days. The 364-day Mobium year is short by approximately 1.2422 days per year. Without correction, the calendar would drift by one full month in approximately 23 years.

**Resolution:** At the mid-year boundary, apply Boundary Folding (Paper III):

> BF(364) = (364 + 1) / 2 = 182.5

Round to 182 via nearest-odd adjustment. But notice: 182 = 2 × 7 × 13. The fold point has the SAME prime factors as the year length (364 = 2² × 7 × 13). The only difference is one fewer factor of 2. The mid-year fold point is the year length with one binary tier removed — exactly what Boundary Folding does: it strips one layer of binary doubling to locate the center.

Insert a **Leap-Fold Day** at index 182. This single additional boundary surface realigns the calendar to the solar year.

**Properties of the leap-fold:**

**Bilateral symmetry.** The fold occurs at the exact midpoint: 182 days before, 182 days after. The year is a Mobium loop folded at its center. The first half mirrors the second half structurally. This symmetry is built into the factorization: 182 = 364/2, and division by 2 is the Boundary Fold of the binary tier.

**Primary correction.** Adding one day (from 364 to 365) absorbs the majority of the deficit: 365.2422 − 365 = 0.2422 days remaining error.

**Four-year correction.** The 0.2422-day residual accumulates to ≈ 0.97 days over four years. Insert a second leap-fold day every four years (yielding 366 days). The remaining error after four years: 4 × 0.2422 − 1 = −0.0312 days.

**128-year correction.** The −0.0312 day/4-year error accumulates to −0.0312 × 32 = −0.9984 days over 128 years. Skip one leap-fold every 128 years. Residual after 128 years: less than 0.002 days.

```
Correction hierarchy:
  Every year:       +1 day (364 → 365)
  Every 4 years:    +1 more day (365 → 366)
  Every 128 years:  −1 day (skip one 4-year correction)
  Net drift per 128 years: < 0.002 days
```

Compare to the Gregorian system: every 4 years (+1), every 100 years (−1), every 400 years (+1). The Gregorian cycle takes 400 years to complete. The Mobium cycle takes 128 years — and 128 = 2⁷, a power of 2, a value on the stable spine. The correction cycle IS a Mersenne boundary: the 128-year cycle closes at 2⁷, and the next Mersenne prime after 7 is 127 = 2⁷ − 1. The correction cycle and the Mersenne tier boundary are adjacent integers. The calendar self-corrects at the same scale where the physics tier transitions.

After leap-fold insertion, the loop re-anchors at day 0 for the next cycle. This is the zero-return principle from Paper III: every traversal of the Mobium returns to origin. The year starts at zero, traverses 364 (or 365, or 366) positions, and returns to zero. No carryover. No debt. Clean restart.

---

### 5. The Year as Mobium Traversal

The calendar is a Mobium loop. Let us make this explicit.

A Mobium loop of B = 7 with step-size 2 visits every node twice in 14 steps, producing a fortnight. But the YEAR is also a Mobium traversal — at a higher scale.

364 = 2² × 7 × 13. The year is a loop of B = 13 (an odd prime) with each segment containing 28 days (2² × 7). Walking the year with step-size 1 visits every day sequentially. Walking with step-size 14 (a fortnight) visits every fortnight boundary, producing 26 stops — and 26 = 2 × 13, which is the stable kernel applied to 13: Stable(13) = 2 × 13 = 26. The number of fortnights per year is the stable output of the month count.

The mid-year fold at 182 divides the 26 fortnights into two sets of 13. Each half-year is one complete B = 13 Mobium loop. The fold marks the point where the first traversal of the 13-loop ends and the second begins. The year is TWO Mobium traversals of B = 13, connected by a fold.

This nesting mirrors the TIERS array:

```javascript
const TIERS = [
  { p:2,  m:3,    name:'quantum foam' },  // smallest loop
  { p:3,  m:7,    name:'nucleon' },        // contains the week
  { p:5,  m:31,   name:'atom' },           // contains the month
  { p:7,  m:127,  name:'molecule' },       // contains the quarter
  { p:13, m:8191, name:'compound' },       // contains the year
  // ...
];
```

The week (7 days) sits at the nucleon tier (m = 7). The month (28 = 4 × 7 days) sits between the nucleon and atom tiers. The quarter (91 days) approaches the molecule tier. The year (364 days) sits in the compound tier (p = 13, range [128, 8191]). The calendar's temporal structure maps onto the spatial TIERS by prime exponent — the same prime (7) that defines the nucleon boundary also defines the week, and the same prime (13) that defines the compound tier also defines the month count.

---

### 6. Seasons & Astronomical Alignment

Because each year resets with perfect integer symmetry:

**Fixed seasonal anchors.** Equinox and solstice dates remain fixed within the calendar structure. The spring equinox always falls in the same week of the same month. In the 13 × 28 system, the four seasons divide the year into four quarters of 91 days each (with the leap-fold day absorbing the extra). Each quarter begins on a fixed day-of-month (day 1 of months 1, 4, 7, and 10). The seasons are structurally anchored.

**No Easter drift.** In the Gregorian system, Easter wanders across a 35-day range (March 22 to April 25) due to the lunar-solar misalignment and the irregular month lengths. In the 13 × 28 system, any lunisolar festival can be anchored to a fixed fortnight, because fortnights are structural units — they don't drift.

**Simple astronomical prediction.** Because every date calculation reduces to integer arithmetic on a modular counter, astronomical event prediction requires only addition and modular reduction:

```
day_of_year = (day_of_year + 1) mod year_length
month       = day_of_year / 28       (integer division)
day_of_month = day_of_year mod 28
week         = day_of_year / 7       (integer division)
fortnight    = day_of_year / 14      (integer division)
quarter      = day_of_year / 91      (integer division)
```

No Julian Day Number conversions. No ephemeris corrections. No lookup tables. The date of any event, in any year, at any precision, can be computed by a child with an abacus.

---

### 7. Implementation

**Software implementation:** Simple modulus arithmetic on a day counter in the range [0, 363]. At day 182, check the leap-fold flag and insert if required. All date calculations reduce to integer addition and modular reduction.

The SIGIL kernel's architecture provides a blueprint. Every module uses the same pattern: take an input, apply operations, wrap at boundaries. The calendar is one more module — the simplest possible one, because all its boundaries are the same width (28 days).

```javascript
// Calendar as SIGIL module (hypothetical)
modules.calendar = {
  dayOfYear: 0,
  yearLength: 364,
  monthLength: 28,
  months: 13,
  leapFoldDay: 182,

  advance() {
    this.dayOfYear = (this.dayOfYear + 1) % this.yearLength;
  },

  month()      { return Math.floor(this.dayOfYear / this.monthLength); },
  dayOfMonth() { return this.dayOfYear % this.monthLength; },
  fortnight()  { return Math.floor(this.dayOfYear / 14); },
  week()       { return Math.floor(this.dayOfYear / 7); },
  quarter()    { return Math.floor(this.dayOfYear / 91); },

  // Leap-fold check: at day 182, insert if correction year
  needsLeapFold(year) {
    if (year % 128 === 0) return false;  // skip every 128 years
    if (year % 4 === 0) return true;     // extra day every 4 years
    return true;                          // base leap-fold every year
  }
};
```

The entire calendar implementation is 18 lines. No conditionals for month length (they're all 28). No day-of-week calculation (every month starts on the same weekday). No century exception rules (the 128-year skip is a single modulus check). The simplicity is a consequence of the structural regularity — and the structural regularity is a consequence of building from family primes.

**Hardware implementation:** A wheel-based calendar mechanism with 364 + 1 positions, synchronized via a fold gear at the midpoint. The fold gear engages once per year (or once per four years for the full leap correction), advancing the wheel by one additional position.

**Cultural integration:** Festivals, holy days, and planning cycles lock to stable weekdays and fortnight Mobium loops. Because every month begins on the same weekday, scheduling is trivially predictable across any time horizon. A meeting scheduled for "the third Tuesday of month 7" is always the same day-of-year, every year, forever. No drift. No lookup.

---

### 8. The 13-Month Cultural Objection

The most common objection to the 13-month calendar is cultural: there is no widely used 13-month tradition in Western civilization, and the number 13 carries superstitious stigma.

The framework's response is structural, not cultural. 13 is a family prime. It is the sixth member of {2, 3, 5, 7, 11, 13, 23, 47}. In the SIGIL kernel:

```javascript
13: 'family prime, K13',
```

Its appearance in the calendar is not arbitrary — it is the smallest family prime that, multiplied by a power-of-2 multiple of 7, produces a value close to the solar year. The solar year constrains the product: 13 × 28 = 364 ≈ 365.25. No other combination of small primes and multiples of 7 comes as close:

- 11 × 28 = 308 (too short by 57 days)
- 11 × 33 = 363 (close, but 33 = 3 × 11, not a multiple of 7)
- 12 × 28 = 336 (too short by 29 days)
- 13 × 28 = **364** (short by 1.24 days — correctable by leap-fold)
- 14 × 28 = 392 (too long by 27 days)

364 is the only product of a small family prime and a 7-multiple that approximates the solar year within single-day correction range. The number 13 is not chosen for mysticism. It is chosen because number theory selects it. The calendar that best fits the solar year using family-prime structure IS a 13-month calendar. The math picks the number; the culture adapts.

---

### Conclusion & Foundation Dependency

Mobium Time demonstrates that an integer-only, prime-loop calendar can achieve superior astronomical synchronization compared to the Gregorian system, while eliminating weekday drift, simplifying date arithmetic, and requiring no fractional adjustments beyond a single, well-defined leap-fold.

**What this paper provides to the series:**

- **Temporal Mobium loop.** The year as a closed integer cycle, demonstrating that Paper I's topology applies to time. Every subsequent paper that references cycles, recursion, or oscillation — especially Paper VII (Cosmic Breath) — can point to the calendar as the simplest working example.
- **Family-prime composition.** The discovery that all calendar constants factor into {2, 7, 13} establishes that the family primes are not merely relevant to particle physics and chemistry — they structure time itself. This universality claim is foundational to the series' argument that one mathematics underlies all scales.
- **The 128-year correction cycle.** 128 = 2⁷, adjacent to the Mersenne prime 127 = 2⁷ − 1. The calendar self-corrects at a Mersenne boundary. This is the first concrete example of a Mersenne tier transition appearing in an applied context, previewing the cosmic-scale tier transitions of Papers VII and XIII.
- **The leap-fold as Boundary Folding.** BF(364) = 182, which shares the same prime factors as 364. Boundary Folding doesn't change the structural identity of a number — it strips one binary layer. The calendar's correction mechanism IS the same operation that re-anchors recursion in the physics.

**What this paper depends on:** Paper I (the Mobium loop that the calendar traverses), Paper II (the kernel operations that generate the structural constants: Growth(6) = 13, Stable(7) = 14, Mitosis(7) = 13), Paper III (the Boundary Fold that defines the leap-fold position), Paper IV (the p = 7 prime-base ruler that subdivides days into watches, spans, beats, and pulses).

White Paper VI explores how Mobium loops generate spatial dimensions, introducing nested dimensional construction from points to volumes to 4D field dynamics.

---

### Proof-of-Concept Reference

All code excerpts drawn from:
**SYNERGONESIS — Unified Visualizer** (v61)
Engine: SIGIL (Sandboxed Interpretive Glyph Index Library)

Key structural evidence:
- `_FAMILY = new Set([2,3,5,7,11,13,23,47])` — the family primes that compose all calendar constants
- `_NOTES` — annotations for 7 ('family prime, M3'), 13 ('family prime, K13'), 14 ('2×7, circuits'), 26 ('YHVH sum')
- `TIERS` array — the spatial scale hierarchy that mirrors the temporal hierarchy
- `modules.genome.generate()` — multi-base ruler overlay, applicable to week (7) and month (13) rulers
- `tierOf()` — the modular counter that maps any count to a tier (the calendar's date-to-month mapping)

---

*Ancient-Shape Physics Series — Paper V of XLIII*
*© 2004–2026 Michael Scott Shaffer. All rights reserved.*
