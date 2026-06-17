# Design Corrections and Clarifications

This file summarizes the main technical clarifications that should be considered when reviewing the handwritten solution drafts.

## Q1 - Largest of Three 3-bit Numbers

The original handwritten draft includes a decoder stage before the seven-segment display. A `3-to-8 decoder` alone is not enough to directly drive a seven-segment display unless additional segment-driving logic is added.

A cleaner implementation is:

```text
A[2:0], B[2:0] -> 3-bit comparator -> 3-bit 2x1 MUX -> MAX_AB
MAX_AB, C[2:0] -> 3-bit comparator -> 3-bit 2x1 MUX -> MAX_ABC
MAX_ABC -> BCD-to-seven-segment decoder -> seven-segment display
```

Since the selected maximum value is only 3 bits, the fourth BCD input can be tied to `0`.

Equality handling is simple: if two values are equal, either value may be selected because both represent the same maximum value.

## Q2 - Bidirectional JK Counter

The counter visits only the even-numbered states:

```text
0 = 000
2 = 010
4 = 100
6 = 110
```

The required sequences are:

```text
X = 1: 0 -> 2 -> 4 -> 6 -> 0
X = 0: 0 -> 6 -> 4 -> 2 -> 0
```

The simplified JK input equations are:

```text
JA = KA = B·X + B'·X'
JB = KB = 1
JC = 0
KC = 1
```

The least significant bit `C` remains `0` because the counter visits only even-numbered states. Setting `JC = 0` and `KC = 1` makes the design more robust: if `C` accidentally becomes `1`, it will be cleared on the next clock edge.

## Q3 - Bank Queue System

A teller register should not directly capture the old counter output during the same button event.

A better timing model is:

```text
NEXT = Counter + 1 mod 10
```

When a teller button is pressed, the counter register and the selected teller register both load `NEXT` on the same clock edge.

```text
P1, P2, P3 = debounced teller button pulses
CALL = P1 + P2 + P3

Counter Register:
Enable = CALL
Input = NEXT

Teller 1 Register:
Enable = P1
Input = NEXT

Teller 2 Register:
Enable = P2
Input = NEXT

Teller 3 Register:
Enable = P3
Input = NEXT
```

The main teller display should hold the teller desk number after the button pulse ends. Therefore, a small main teller register can be used:

```text
Load 1 when P1 is pressed
Load 2 when P2 is pressed
Load 3 when P3 is pressed
```

## Operating Assumptions

- Push buttons are assumed to be debounced.
- Only one teller button is assumed to be pressed at a time.
- If simultaneous button presses must be supported, a priority encoder should be added.
- Customer numbers wrap from `9` back to `0`.
