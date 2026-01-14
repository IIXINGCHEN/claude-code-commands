---
description: Create a detailed summary of the conversation for context compression
argument-hint: [output-filename]
---

# Context Compression: Generate Conversation Summary

## Overview

Create a comprehensive summary of the current conversation to enable context compression for long-running discussions. The summary captures technical details, decisions, and state to allow continuing work efficiently.

## Output File

Write the summary to: `.agents/context-summaries/$ARGUMENTS` (default: `context-summary.md`)

## Summary Structure

### Required Sections

**1. Context**
- How to continue the conversation
- Previous conversation high-level flow
- Current work being performed
- Key technical concepts and decisions
- Relevant files and code examined or modified
- Problems solved and ongoing troubleshooting
- Pending tasks and next steps

**2. Previous Conversation**
- Detailed description of what was discussed
- Overall conversation flow and goals
- Key decisions made

**3. Current Work**
- What was being worked on before this summary request
- Special attention to recent messages
- Current task status

**4. Key Technical Concepts**
- List all important technical concepts
- Technologies used
- Coding conventions and patterns
- Frameworks discussed

**5. Relevant Files and Code**
- Enumerate specific files examined or modified
- Why each file is important
- Changes made to files
- Include important code snippets

**6. Problem Solving**
- Problems that have been solved
- Ongoing troubleshooting efforts
- Issues encountered and resolutions

**7. Pending Tasks and Next Steps**
- All tasks explicitly asked to work on
- Next steps for outstanding work
- Include direct quotes from conversation for context
- What was being worked on and where left off

## Instructions

### 1. Gather Information
- Review the entire conversation history
- Identify explicit requests and actions taken
- Note technical decisions and patterns
- Capture file changes and code modifications

### 2. Synthesize Content
- Organize information into appropriate sections
- Preserve technical details and code examples
- Maintain chronological flow of conversation
- Include direct quotes where they add clarity

### 3. Write the Summary
- Use clear, professional language
- Follow the structured sections defined above
- Use markdown formatting (headings, lists, code blocks)
- Include code snippets for technical content
- Keep sections concise but comprehensive

### 4. Quality Checks
- All required sections present
- Technical details preserved accurately
- Recent work clearly documented
- Next steps actionable and clear
- File references are accurate
- Direct quotes included where appropriate

## Style Guidelines

- **Tone:** Professional, clear, detailed
- **Format:** Use markdown extensively (headings, lists, code blocks, tables)
- **Specificity:** Preserve concrete examples and technical specifics
- **Length:** Comprehensive to ensure no context loss
- **Quotations:** Include verbatim quotes for pending tasks

## Output Confirmation

After creating the summary:
1. Confirm the file path where it was written
2. Provide a brief summary of what was captured
3. Highlight any important context that was preserved
4. Suggest how this summary can be used for context restoration

## Notes

- This summary is designed for context compression in long conversations
- Include all relevant technical details for accurate context restoration
- Preserve code patterns and architectural decisions
- Document pending work clearly for seamless continuation
- This command contains the complete summary template structure - no external references needed
