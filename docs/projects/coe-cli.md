# COE CLI (coe-cli.cjs)

!!! success "Active — 9 Prompt Modules"

---

## Overview

The COE CLI is a Node.js CommonJS CLI runner that generates structured prompts for Claude and includes a Copilot Handoff Block. It serves as the command-line backbone for Qasim's dual-agent workflow, enabling rapid, repeatable prompt generation for complex appraisal and pricing tasks.

The project is maintained in the `claude-plugins-official` repository and currently comprises nine active prompt modules.

---

## Prompt Modules

The CLI includes specialized modules for different aspects of the pricing and appraisal workflow.

| Module | Purpose |
|---|---|
| **VIN Intelligence Scan** | Generates structured prompts for VIN-based vehicle identification and risk assessment |
| **Price Normalization Engine** | Standardizes pricing data across multiple market sources |
| **Market Benchmark** | Compiles UAE market pricing from seven platforms |
| **GCC/Non-GCC Verification** | Validates vehicle specification origin |
| **Accident History Check** | Structures MOI accident data interpretation |
| **Autorola Comment Injection** | Prepares internal comments for Autorola appraisals |
| **Trade-In Decision Logic** | Generates ACQUIRE / NEGOTIATE / DECLINE recommendations |
| **Copilot Handoff Block** | Formats outputs for seamless transfer to Microsoft Copilot |
| **Valuation Summary** | Produces executive-ready valuation summaries |

---

## Technical Details

The CLI was developed as a CommonJS module (`coe-cli.cjs`) to resolve ESM/CommonJS conflicts encountered on Windows Git Bash. This pragmatic decision ensured compatibility across Qasim's development environment (corporate laptop with Git Bash, Node.js v24).

```
Repository: claude-plugins-official
Runtime:    Node.js (CommonJS)
Entry:      coe-cli.cjs
Platform:   Windows 11 / Git Bash
```

---

## Integration with Dual-Agent Architecture

The COE CLI is a critical component of the [Dual-Agent Architecture](dual-agent-architecture.md). It generates the structured prompts that Claude uses for external research (VIN decoding, market benchmarking, accident interpretation), and its Copilot Handoff Block ensures that outputs can be seamlessly consumed by Microsoft Copilot for internal appraisal logic.
