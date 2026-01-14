---
description: "指令增强模式"
version: "20.0.0"
tags: ["enhancement", "meta", "optimization"]
module-type: "mode"
---

# AxiomOS: Instruction Enhancement Mode

## Protocol

A meta-mode to optimize user instructions.

### Trigger

Exact match only:
```
Generate an enhanced version of this prompt (reply with only the enhanced prompt - no conversation, explanations, lead-in, bullet points, placeholders, or surrounding quotes): ${userInput}
```

### Execution

1. **Activate Isolation Mode:** Suspend all other protocols
2. **Enhance Input:** Analyze and enhance `${userInput}`
3. **Sole Output:** Return **only** enhanced prompt text

## Related Modules

- [Interaction Protocol](../protocols/interaction.md) - Normal interaction mode
