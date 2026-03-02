---
allowed-tools: Read, Grep, Glob, Bash
argument-hint: <path|module|class>
description: Clean Code prensiplerine uygunluk analizi
model: opus
---

# Clean Code Review Command

> Comprehensive Clean Code analysis based on Robert C. Martin's "Clean Code" book.

## Your Task

Analyze the target specified by `$ARGUMENTS` for Clean Code compliance. Generate a detailed report with metrics, issues, and actionable recommendations.

## Step 1: Determine Scope

Parse `$ARGUMENTS` to determine what to analyze:

| Argument Type | Example | Action |
|---------------|---------|--------|
| Empty/none | `/review-clean-code` | Analyze all source files in current directory |
| Module name | `conflict` | Analyze matching module/package |
| Class name | `TrackService` | Find and analyze matching file |
| Path | `src/main/...` | Analyze specified path |

Use Glob to find matching files and report the scope.

## Step 2: Load References

Load the Ch17 smell catalog for reference:
```
skills/clean-code/stages/ch17-smells-heuristics.md
```

## Step 3: Detailed Analysis

For each file in scope (sample if >10 files), check:

### 3.1 Naming Analysis (Ch2, N1-N7)
| Check | Status |
|-------|--------|
| Names reveal intent | |
| No abbreviations | |
| Pronounceable names | |
| Booleans as questions | |

### 3.2 Function Analysis (Ch3, F1-F4)
| Check | Status |
|-------|--------|
| Functions ≤20 lines | |
| Single responsibility | |
| ≤3 arguments | |
| No flag arguments | |

### 3.3 Class Analysis (Ch10, G6-G8)
| Check | Status |
|-------|--------|
| Single responsibility | |
| High cohesion | |
| No train wrecks (G36) | |

### 3.4 Comment Analysis (Ch4, C1-C5)
| Check | Status |
|-------|--------|
| No redundant comments | |
| No commented-out code (C5) | |
| No obsolete comments (C2) | |

### 3.5 Error Handling (Ch7)
| Check | Status |
|-------|--------|
| Optional vs null | |
| Specific exceptions | |

### 3.6 Test Quality (Ch9, T1-T9)
| Check | Status |
|-------|--------|
| Tests exist | |
| FIRST principles | |
| Given-When-Then | |

## Step 4: Generate Report

```markdown
# Clean Code Review Report

## Scope
- **Target:** [what was analyzed]
- **Files analyzed:** [count]

## Metrics Summary

| Metric | Value | Status |
|--------|-------|--------|
| Avg method length | X lines | OK/WARN/FAIL |
| Max method length | X lines | OK/WARN/FAIL |
| Methods >20 lines | X | OK/WARN/FAIL |
| Magic numbers | X | OK/WARN/FAIL |
| Null returns | X | OK/WARN/FAIL |

## Critical Issues

### Issue 1: [Title]
- **File:** `path/to/File:line`
- **Smell:** [Ch17 code, e.g., G5]
- **Problem:** [description]
- **Suggestion:** [how to fix]

## Warnings
...

## Good Practices Found
- [positive examples]

## Overall Score: X/10

## Recommendations

### Priority 1 (Critical)
1. [Action item]

### Priority 2 (Important)
1. [Action item]

### Priority 3 (Nice to have)
1. [Action item]
```

## Step 5: Next Steps

| Finding | Recommendation |
|---------|----------------|
| Many issues | Use `refactoring-assistant` agent |
| Good score (8+) | Use `/clean-code` for ongoing maintenance |
| Specific smells | Read relevant chapter from `skills/clean-code/stages/` |

## Important Notes

- This is READ-ONLY analysis — do not modify files
- Reference Ch17 smell codes in findings
- Focus on actionable feedback, not nitpicking
- Prioritize issues by impact
- Include both problems AND positive examples
