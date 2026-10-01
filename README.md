# safe-multi-agent-github-dev-skill

High-strictness multi-perspective development skill for safe GitHub workflows.

This skill forces the agent to simulate multiple specialized agents (Designer, Implementer, Security-Critic, Performance-Critic, Code-Reviewer), make them critique each other, and have a Judge select the single best approach before any code changes.

It also enforces extremely strict file-safety rules and automatic backups when working with GitHub repositories.

## Key Features

- Simulated multi-agent proposals + mutual critique
- Final Judge scoring on correctness, safety, risk of file loss, maintainability, and completeness
- Mandatory safety branch or tag before large/destructive changes
- Prefer Pull Requests over direct pushes to main
- Explicit user confirmation required before any GitHub write access
- Automatic backups at the start of major tasks and after commits that touch more than 3 files

## How to Use in Grok

1. Place the `SKILL.md` (or the whole skill folder) into your Grok skills directory:
   `/home/workdir/.grok/skills/safe-multi-agent-github-dev/`

2. The skill activates automatically when you use trigger phrases such as:
   - multi-agent
   - critique each other
   - judge the best approach
   - safe GitHub edit
   - backup before change
   - high-safety development

3. For GitHub write operations the agent will always ask for explicit confirmation in the current conversation before making any changes.

## Safety Philosophy

This skill prioritizes zero accidental file loss. It will refuse to proceed if:
- GitHub write access has not been confirmed in the current conversation
- No safety branch/tag exists before a large change
- The Judge has not selected a single winning approach
- Destructive actions lack explicit user confirmation

## License

This skill is provided as-is for personal and open-source use.
