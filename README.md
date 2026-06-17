# Digital Logic Final Assignment

This repository contains my handwritten solution for a first-year Digital Logic final assignment.

The assignment was originally submitted as a paper-based design task, so the main solution is preserved as scanned handwritten drafts. Additional notes are included to clarify the design decisions, later corrections, and recommended improvements.

## Assignment Overview

The assignment includes three digital logic design problems:

1. **Largest of Three 3-bit Numbers**  
   Design a circuit that compares three 3-bit numbers and displays the largest value on a seven-segment display.

2. **Bidirectional JK Counter**  
   Design a JK flip-flop counter that counts through the even-numbered states in one direction when `X = 1`, and in the reverse direction when `X = 0`.

3. **Bank Queue System**  
   Design a simple queue system for three bank tellers using one counter, three push buttons, five seven-segment displays, teller registers, and display-selection logic.

## Concepts Used

- 3-bit comparators
- Multiplexers
- JK flip-flops
- D flip-flops / registers
- Karnaugh maps
- BCD incrementer
- BCD decade counter
- BCD-to-seven-segment decoders
- Push-button controlled sequential logic
- Basic gate-level design

## Repository Structure

```text
digital-logic-final-assignment/
│
├── README.md
├── assignment/
│   └── Digital_Final_assignment.docx
│
├── handwritten-solution/
│   ├── 01-bank-queue-initial-block-diagram.jpg
│   ├── 02-bcd-incrementer-concept.jpg
│   ├── 03-jk-counter-kmap-and-gate-draft.jpg
│   ├── 04-q1-comparator-and-q2-state-table.jpg
│   ├── 05-bcd-counter-gate-level-draft.jpg
│   └── 06-bank-queue-display-selection-draft.jpg
│
├── notes/
│   └── design-corrections.md
│
├── docs/
│   └── github-upload-commands.md
│
├── .gitignore
└── LICENSE
```

## Handwritten Solution Pages

| Page | Description |
|---|---|
| [`01-bank-queue-initial-block-diagram.jpg`](handwritten-solution/01-bank-queue-initial-block-diagram.jpg) | Initial block diagram draft for the bank queue system. |
| [`02-bcd-incrementer-concept.jpg`](handwritten-solution/02-bcd-incrementer-concept.jpg) | BCD incrementer concept used for advancing the customer number. |
| [`03-jk-counter-kmap-and-gate-draft.jpg`](handwritten-solution/03-jk-counter-kmap-and-gate-draft.jpg) | K-map simplification and gate-level draft for the JK counter. |
| [`04-q1-comparator-and-q2-state-table.jpg`](handwritten-solution/04-q1-comparator-and-q2-state-table.jpg) | Comparator sketch and state-transition table draft. |
| [`05-bcd-counter-gate-level-draft.jpg`](handwritten-solution/05-bcd-counter-gate-level-draft.jpg) | BCD decade counter truth-table, K-map, and gate-level design draft. |
| [`06-bank-queue-display-selection-draft.jpg`](handwritten-solution/06-bank-queue-display-selection-draft.jpg) | Final display-selection draft for the bank queue system. |

## Important Clarifications

The handwritten pages document the original design process. Some later clarifications are included in [`notes/design-corrections.md`](notes/design-corrections.md), especially regarding:

- Using a BCD-to-seven-segment decoder instead of assuming a 3-to-8 decoder can directly drive a display.
- Keeping the least significant counter bit fixed for the even-state JK counter.
- Loading teller registers with the incremented customer number instead of the old counter value.

## Status

This project is archived as an early undergraduate coursework project and is kept mainly for learning documentation and portfolio purposes.
