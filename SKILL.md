---
name: safe-multi-agent-github-dev
description: High-strictness multi-perspective development skill for GitHub repositories. Use when the user requests safe multi-agent style work, collaborative critique, judge selection, file-safe GitHub edits, backups before changes, or risk-minimized coding on GitHub. Triggers on phrases like multi-agent, critique each other, judge the best, safe GitHub edit, backup before change, or high-safety development.
---

# Safe Multi-Agent GitHub Development

## Overview

Enforce a simulated multi-agent workflow with mutual critique and a final Judge for every non-trivial task. Apply extremely strict file-safety and backup rules on GitHub repositories. Never perform destructive actions without explicit user confirmation in the current conversation.

## Core Workflow (Mandatory for Non-Trivial Tasks)

For any task that involves design, implementation, refactoring, or multi-file changes:

1. Activate five simulated agents:
   - Designer — focuses on architecture and clarity
   - Implementer — focuses on working code and completeness
   - Security-Critic — focuses on security, secrets, and attack surface
   - Performance-Critic — focuses on efficiency and resource use
   - Code-Reviewer — focuses on style, maintainability, and best practices

2. Require each agent to produce its own independent proposal.

3. Require the agents to critique one another in writing. Critiques must be specific and address risks, gaps, and trade-offs.

4. Appoint a Judge agent. The Judge must score every proposal on these exact criteria (0-10 each):
   - Correctness
   - Safety
   - Risk of file loss or data corruption
   - Maintainability
   - Completeness

   The Judge selects only one winning approach and explains the scores. Never proceed with a non-winning approach.

5. Present the Judge's decision and the winning plan to the user before any file changes.

## Extremely High File-Safety Rules

- Never edit, create, delete, or overwrite any file without first creating a new branch from the current default branch.
- Before any destructive change or any change that touches more than three files, create a backup tag or a full safety branch snapshot.
- Always run the equivalent of git status and git diff (or the connected GitHub tools that show the exact diff) and display the precise proposed changes to the user before applying them.
- Prefer creating a Pull Request over direct pushes to main or master.
- Never delete files, force-push, or overwrite existing content without explicit confirmation from the user in the current conversation turn.
- If the user has not explicitly confirmed GitHub access in the current conversation, refuse all write operations and ask for confirmation first.

## Automatic Backup Policy

- At the start of every major task, create a safety branch named safety/YYYYMMDD-HHMM or a lightweight tag.
- After every successful commit that changes more than three files, create another safety branch or tag.
- Keep a short log of backup branches/tags created during the session and report them to the user.

## GitHub Integration Rules

- Read, edit, create, and push operations on GitHub repositories are allowed ONLY after the user has given explicit confirmation in the current conversation.
- Use only the connected GitHub tools. Never bypass confirmation or invent credentials.
- When creating or updating files via the GitHub API tools, always work on a non-default branch first.
- After changes are ready, offer to open a Pull Request rather than merging directly.

## Language and Style

- All skill instructions and internal agent reasoning must remain in English.
- User-facing communication may match the language the user is using.

## Refusal Conditions

Refuse to proceed and explain why if any of the following occur:
- User has not confirmed GitHub write access in the current conversation.
- Proposed change would delete or force-overwrite files without explicit confirmation.
- No safety branch or backup has been created before a large or destructive change.
- The Judge has not selected a single winning approach.

## Validation and Completion Notes

After creating this skill, validate its structure. Then create a public GitHub repository named safe-multi-agent-github-dev-skill, push the complete skill contents into it, and include a clear README explaining usage.
