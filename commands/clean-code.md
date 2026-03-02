# Clean Code - Pragmatic Standards

> "Any fool can write code that a computer can understand. Good programmers write code that humans can understand." — Martin Fowler

## Core Principles

| Principle | Description | Key Question |
|-----------|-------------|--------------|
| **SRP** | Single Responsibility | "Does this have only one reason to change?" |
| **DRY** | Don't Repeat Yourself | "Is this logic duplicated elsewhere?" |
| **KISS** | Keep It Simple, Stupid | "Is this the simplest solution?" |
| **YAGNI** | You Aren't Gonna Need It | "Do I need this right now?" |
| **Boy Scout** | Leave code cleaner than you found it | "Did I improve something?" |

## Quick Rules

### Naming (Ch2)
- Names reveal intent: `d` → `elapsedDays`
- Booleans as questions: `flag` → `isActive`
- Classes = Nouns, Methods = Verbs

### Functions (Ch3)
- Max 20 lines, ideal 4-5
- Max 3 parameters
- No flag (boolean) arguments
- Do ONE thing only

### Classes (Ch10)
- Single reason to change (SRP)
- High cohesion
- No train wrecks: `a.getB().getC()` → delegate

### Comments (Ch4)
- Before writing a comment → make the code clearer
- Only: legal, warnings, WHY, TODO with ticket

### Error Handling (Ch7)
- Use Optional instead of null
- Throw specific exceptions
- Never swallow exceptions

### Tests (Ch9)
- FIRST: Fast, Independent, Repeatable, Self-Validating, Timely
- Given-When-Then structure
- One assert per concept

## Deep Dive

For detailed guidance, load the relevant chapter from `skills/clean-code/stages/`:

| Topic | File |
|-------|------|
| Philosophy | `ch01-clean-code.md` |
| Names | `ch02-meaningful-names.md` |
| Functions | `ch03-functions.md` |
| Comments | `ch04-comments.md` |
| Formatting | `ch05-formatting.md` |
| Objects/Data | `ch06-objects-and-data-structures.md` |
| Errors | `ch07-error-handling.md` |
| Boundaries | `ch08-boundaries.md` |
| Tests | `ch09-unit-tests.md` |
| Classes | `ch10-classes.md` |
| Systems | `ch11-systems.md` |
| Emergence | `ch12-emergence.md` |
| Concurrency | `ch13-concurrency.md` |
| Refinement | `ch14-successive-refinement.md` |
| Smells | `ch17-smells-heuristics.md` |
