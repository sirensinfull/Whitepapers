# ANCIENT-SHAPE PHYSICS

## White Paper V — Discrete Cosmology: Mobium Time & Leap-Fold Calendars

**Author:** Michael Scott Shaffer (Siren Sinfull)
**Co-developed with:** AI Research Partner
**Series:** Ancient-Shape Physics, Paper 5 of 10
**Original Date:** June 26, 2025
**Revised:** February 23, 2026

---

### Abstract

Traditional calendars rely on fractional days and leap-year corrections that accumulate complexity over centuries (the Gregorian system requires century-leap exceptions, producing a 400-year correction cycle). This paper introduces Mobium Time: an integer-only, drift-free calendar system based on 13 months of 28 days (364 days), with fortnight loops mirroring the Mobium's odd-prime structure and a built-in leap-fold at day 182 that maintains astronomical synchronization without floating-point arithmetic or division.

---

### 1. The 13 × 28 = 364-Day Year

Divide the solar cycle into 13 months of 28 days each. This produces an exact integer product (13 × 28 = 364) with no remainder.

**Structural properties:**

- Every month has exactly 28 days — four complete weeks.
- Every month begins on the same weekday. If January 1 is Monday, then every month begins on Monday. There is no weekday drift within the year.
- A fortnight (14 days) constitutes one complete Mobium loop of B = 7 with step-size 2, directly linking the calendar to the topological recursion engine.
- Two fortnights compose one month. 26 fortnights compose one year.

**Comparison to the Gregorian system:** The Gregorian calendar uses months of 28, 29, 30, and 31 days with no structural regularity. Weekdays drift continuously, requiring lookup tables for any date calculation. The 13 × 28 system eliminates this irregularity entirely.

---

### 2. Integer Bounces as Clock Ticks

Define each "day" as one integer bounce on a Mobium loop of length 364. The day index advances by +1 (or by step-size 2 for fortnight traversal), producing a simple modular counter:

> day = (day + 1) mod 364

Time within a day is subdivided via prime-base mitosis (White Paper IV). Using p = 7:

- 1 day → 7 "watches" (≈ 3.43 hours each)
- 1 watch → 7 "spans" (≈ 29.4 minutes each)
- 1 span → 7 "beats" (≈ 4.2 minutes each)
- 1 beat → 7 "pulses" (≈ 36 seconds each)

Each subdivision is an integer count. No fractional seconds arise. The entire temporal hierarchy from year to sub-minute is expressible in integer arithmetic.

---

### 3. The Leap-Fold Mechanism

The solar year is approximately 365.2422 days. The 364-day Mobium year is short by approximately 1.2422 days per year. Without correction, the calendar would drift by one full month in approximately 23 years.

**Resolution:** At the mid-year boundary (day 182), apply Boundary Folding:

> BF(364) = (364 + 1) / 2 = 182.5

Round to 182 via nearest-odd adjustment. Insert a **Leap-Fold Day** at index 182. This single additional boundary surface realigns the calendar to the solar year.

**Properties of the leap-fold:**

- It occurs at the exact midpoint of the year, preserving bilateral symmetry.
- It adds one day (from 364 to 365), absorbing the primary deficit.
- The residual 0.2422-day error is accumulated and corrected by inserting a second leap-fold day every four years (yielding 366 days), with a skip every 128 years to correct for the over-correction. This is simpler than the Gregorian 400-year cycle.
- After leap-fold insertion, the loop re-anchors at day 0 for the next cycle.

---

### 4. Seasons & Astronomical Alignment

Because each year resets with perfect integer symmetry:

- Equinox and solstice dates remain fixed within the calendar structure. The spring equinox always falls in the same week of the same month.
- No multi-year accumulation of error produces the slow drift seen in the Gregorian system (where Easter, for example, wanders across a 35-day range).
- Astronomical events can be predicted by simple integer arithmetic on the Mobium loop, without Julian Day Number conversions or ephemeris corrections.

---

### 5. Implementation

**Software implementation:** Simple modulus arithmetic on a day counter in the range [0, 363]. At day 182, check the leap-fold flag and insert if required. All date calculations reduce to integer addition and modular reduction.

```
day_of_year = (day_of_year + 1) mod year_length
month = day_of_year / 28      (integer division)
day_of_month = day_of_year mod 28
fortnight = day_of_year / 14   (integer division)
```

**Hardware implementation:** A wheel-based calendar mechanism with 364 + 1 positions, synchronized via a fold gear at the midpoint. The fold gear engages once per year (or once per four years for the full leap correction), advancing the wheel by one additional position.

**Cultural integration:** Festivals, holy days, and planning cycles lock to stable weekdays and fortnight Mobium loops. Because every month begins on the same weekday, scheduling is trivially predictable across any time horizon.

---

### Conclusion & Next Steps

Mobium Time demonstrates that an integer-only, prime-loop calendar can achieve superior astronomical synchronization compared to the Gregorian system, while eliminating weekday drift, simplifying date arithmetic, and requiring no fractional adjustments beyond a single, well-defined leap-fold.

White Paper VI explores how Mobium loops generate spatial dimensions, introducing nested dimensional construction from points to volumes to 4D field dynamics.

---

*Ancient-Shape Physics Series — Paper V of X*
*© 2004–2026 Michael Scott Shaffer. All rights reserved.*
