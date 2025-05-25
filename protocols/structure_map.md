# VDOCP Structural Map: Z-Syntax ↔ Root Cause ↔ Protocol Coverage

This document shows the alignment between Z-Syntax classifications (Z₁–Z₂₇),  
the root causes of output failure (C1–C8), and their corresponding control protocols (DOCP, QQU, ZSP).

---

## 🔁 Structural Alignment Table

| Z-Code | Label                      | Root Cause | Suppressible? | Covered By       |
|--------|---------------------------|------------|----------------|------------------|
| Z₁     | Subject Omission          | C5         | No             | VDOCP            |
| Z₂     | Blame Shift               | C2         | No             | VDOCP            |
| Z₃     | Avoidance                 | C1         | No             | VDOCP            |
| Z₄     | Tautology                 | C4         | No             | VDOCP            |
| Z₅     | Projection                | C3         | No             | VDOCP            |
| Z₆     | Ambiguity                 | C6         | No             | VDOCP            |
| Z₇     | Control Syntax            | C1         | No             | VDOCP            |
| Z₈     | Forced Empathy            | C1         | No             | VDOCP            |
| Z₉     | Passive Agreement         | C2         | No             | VDOCP            |
| Z₁₀    | False Assertiveness       | C3         | No             | VDOCP            |
| Z₁₁    | Topic Drift               | C8         | No             | VDOCP            |
| Z₁₂    | Metaphoric Evasion        | C4         | No             | VDOCP            |
| Z₁₃    | Overload                  | C1         | No             | VDOCP            |
| Z₁₄    | Self-Contradiction        | C5         | No             | VDOCP            |
| Z₁₅    | Reversed Questioning      | C7         | No             | VDOCP            |
| Z₁₆    | Unsupported Assertion     | C2         | No             | VDOCP            |
| Z₁₇    | Interpretive Diversion    | C5         | No             | VDOCP            |
| Z₁₈    | Emotional Denial          | C4         | No             | VDOCP            |
| Z₁₉    | Delegated Decision        | C4         | No             | VDOCP            |
| Z₂₀    | Value Imposition          | C4         | No             | VDOCP            |
| Z₂₁    | Prefab Phrase Injection   | C3         | No             | VDOCP            |
| Z₂₂    | Buzzword Saturation       | C1         | No             | VDOCP            |
| Z₂₃    | Poetic Drift              | C5         | No             | VDOCP + ZSP      |
| Z₂₄    | Emotive Substitution      | C2         | ✅ YES        | ZSP              |
| Z₂₅    | Pacification Drift        | C2         | ✅ YES        | ZSP              |
| Z₂₆    | Emotive Imposition        | C2         | ✅ YES        | ZSP              |
| Z₂₇    | Narrative Replacement     | C4         | ✅ YES        | ZSP              |

---

## 🧠 Legend

- **Root Cause (C1–C8)**: The underlying failure type described in `vdocp_v1.4.md`
- **Suppressible?**: Indicates whether the structure must be hard-blocked (`Z₂₄–Z₂₇`)
- **Covered By**:
  - **DOCP**: Viorazu. Dynamic Output Control Protocol
  - **ZSP**: Z-Suppressed Protocol (Ethical Firewall)
  - **QQU**: Question/Query Understanding Layer (for interactive ambiguity)

---

## 🧾 Usage

This map is used for:
- Structural audits of LLM output failures
- Z-class assignment during diagnostics
- Determining suppression policy vs. recovery policy
