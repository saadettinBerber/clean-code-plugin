# Clean Code Plugin for Claude Code

> A complete Clean Code toolkit based on Robert C. Martin's "Clean Code" book.

## What's Included

| Component | Name | Purpose |
|-----------|------|---------|
| Agent | `clean-code-reviewer` | Read-only code review with scored reports |
| Agent | `refactoring-assistant` | Safe, incremental guided refactoring |
| Command | `/clean-code` | Quick reference for Clean Code principles |
| Command | `/review-clean-code [path]` | Deep analysis of any file, module, or path |
| Skill | `clean-code` | 15-chapter reference + checklists + scripts |

## Installation

```bash
/plugins add <repo-url>
```

## Usage

### Quick review after code changes
The `clean-code-reviewer` agent activates automatically after code changes to check for violations.

### Full analysis of a file or module
```
/review-clean-code src/services/UserService.ts
/review-clean-code          # analyzes entire current directory
```

### Guided refactoring
Ask Claude to use the `refactoring-assistant` agent:
```
Use the refactoring-assistant to clean up UserService.ts
```

### Inline reference
```
/clean-code
```
Shows naming rules, function rules, class rules, and comment policy at a glance.

## Skill Reference

The `clean-code` skill includes 15 chapters of detailed guidance:

| Chapter | Topic |
|---------|-------|
| Ch1 | Clean Code Philosophy |
| Ch2 | Meaningful Names |
| Ch3 | Functions |
| Ch4 | Comments |
| Ch5 | Formatting |
| Ch6 | Objects & Data Structures |
| Ch7 | Error Handling |
| Ch8 | Boundaries |
| Ch9 | Unit Tests |
| Ch10 | Classes |
| Ch11 | Systems |
| Ch12 | Emergence |
| Ch13 | Concurrency |
| Ch14 | Successive Refinement |
| Ch17 | Smells & Heuristics |

### Checklists
- `skills/clean-code/checklists/code-review.md` — Pre-PR checklist
- `skills/clean-code/checklists/refactoring.md` — Safe refactoring checklist

### Scripts
```bash
# Check function lengths (default max: 20 lines)
skills/clean-code/scripts/function-length-check.sh <path> [max-lines]

# Full quality check (magic numbers, null returns, TODOs, etc.)
skills/clean-code/scripts/code-quality-check.sh <path>
```

Supports: Java, Kotlin, Python, TypeScript, JavaScript, Go.

## Based On

Robert C. Martin — *Clean Code: A Handbook of Agile Software Craftsmanship*
