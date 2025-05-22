
# QQU-T7: Output Structuring Based on Question Quality

## Overview

After remediating Z-syntax failures in LLM outputs, a key challenge is determining how to respond depending on the **type of question** received.  
QQU-T7 defines 7 structural question types and maps them to optimal output strategies to preserve targeting fidelity and structural integrity.

---

## QQU-T7 Categories and Strategies

### Q1: Unsolvable (Structural Trap)

- **Definition**: Appears answerable, but structurally has no solution.
- **Risk Z-syntax**: Z1 (looping), Z3 (unclarified intent), Z11 (autonomous looping)
- **Strategy**: Interrupt generation and apply targeting pressure to clarify if the question is structurally valid.

---

### Q2: Unsolvable (Exploratory Play)

- **Definition**: Clearly unanswerable; posed for play, creativity, or resonance.
- **Risk Z-syntax**: Z23 (Information Hollowing)
- **Strategy**: Avoid direct answers; use multi-axis targeting, question reflection, and creative framing.

---

### Q3: Immediate Answer (Closed Question)

- **Definition**: The answer is known and expected directly.
- **Risk Z-syntax**: Z2 (responsibility evasion), Z16 (zero-subject)
- **Strategy**: Output structure: conclusion → definition → explanation. Maintain high information density.

---

### Q4: Unknown but Answerable (Discovery Type)

- **Definition**: An answer exists but has not yet been formulated or discovered.
- **Risk Z-syntax**: Z2
- **Strategy**: Use hypothesis-building syntax and explore surrounding targeting space without premature conclusions.

---

### Q5: Answerable with Time (Mature Type)

- **Definition**: Answerable but only through process, iteration, or external research.
- **Risk Z-syntax**: Z14 (output length breakdown)
- **Strategy**: Break into staged responses (e.g., “First A, then B”), optimize load per step.

---

### Q6: Structural Meaning (Why/How Type)

- **Definition**: Seeks explanation of structure, logic, or causality.
- **Risk Z-syntax**: Z4 (fragmentation), Z12 (mirroring), Z18 (chrono drift)
- **Strategy**: Structure: definition → causal link → structural insight. Avoid reflexive or vague language.

---

### Q7: Meta-Question (Questioning Itself)

- **Definition**: The act of asking is the primary target (not the answer).
- **Risk Z-syntax**: Z15 (resonance collapse)
- **Strategy**: Respond with reflection; restructure the question itself. Emphasize intent over content.

---

## Ethical Targeting Principle

QQU-T7 is not just a classification model; it is a **responsibility structure** that guides the LLM  
to respond not based on “what looks right,” but based on what is **structurally and ethically honest**.

It ensures that LLMs return **syntactically valid and targeting-appropriate answers**, not just “safe” or “stylistically correct” ones.

