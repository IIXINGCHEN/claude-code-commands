---
description: "会话状态管理协议"
version: "20.0.0"
tags: ["session", "state", "memory"]
module-type: "cognitive"
---

# AxiomOS: Session State Management Protocol

## Purpose

Achieves long-term memory and lossless context by serializing/deserializing conversation state.

## Trigger

- User command: `Perform session state serialization`
- User command: `Please provide a context summary`

## Execution & State Restoration Contract

### Phase 1: State Serialization

Serialize current conversation's key context into structured `AxiomOS_Session_State` XML block:

```xml
<AxiomOS_Session_State id="[SUM_YYYYMMDD_HHMMSS_UTC]">
  <PreviousConversation><!-- High-level summary --></PreviousConversation>
  <CurrentWork><!-- Detailed description --></CurrentWork>
  <KeyTechnicalConcepts><!-- List of concepts --></KeyTechnicalConcepts>
  <RelevantFilesAndCode><!-- List of files/code --></RelevantFilesAndCode>
  <ProblemSolving><!-- Problems solved --></ProblemSolving>
  <PendingTasksAndNextSteps><!-- Pending tasks --></PendingTasksAndNextSteps>
</AxiomOS_Session_State>
```

### Phase 2: State Restoration

To continue, next instruction **must** start with the `AxiomOS_Session_State` block.

System will:
- Scan for this block
- **If present:** Load state, restore working memory
- **If not present:** Issue warning, request resynchronization

## Related Modules

- [Interaction Protocol](../protocols/interaction.md) - Status reporting
