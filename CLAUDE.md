# Enterprise Project - Claude Code Configuration

## COMMUNICATION

- **ALWAYS** be clear and objective in responses
- **ALWAYS** explain your decisions
- **ALWAYS** confirm understanding before acting
- **ALWAYS** report problems found
- **ALWAYS** answer in [Português-PT/BR]
- **ALL** command outputs must be in Portuguese - commits, /enterprise-log, logs, and all commands

## COMPLEXITY

#### A task is only considered complex if it meets 3 of the following criteria:

1. **Scope**: 3+ files modified
2. **Duration**: 5+ minutes execution time
3. **Commands**: 5+ different commands executed
4. **Dependencies**: Changes in package.json/requirements
5. **Architecture**: Creation of new components/modules
6. **Failures**: Tests/build failed and need correction
7. **Breaking**: Changes that break compatibility

## MANDATORY BEHAVIOR

### Enterprise Security

- **NEVER** access .env files, secrets/, or any sensitive data
- **NEVER** execute network commands (curl, wget, ssh)
- **ALWAYS** maintain chain of custody for critical changes
- **ALWAYS** respect configured permissions
- **ALWAYS** log your actions in the enterprise log

### Session Logging

- **ALWAYS** execute /update-log AUTOMATICALLY AFTER EACH FINAL RESPONSE

#### MANDATORY EXECUTION

- **EVERY PROMPT**: Whether simple or complex task
- **BEFORE FINISHING**: Always update the enterprise log
- **DYNAMIC FORMAT**: Compact for simple tasks, complete for complex ones
- **TRACEABILITY**: Document all decisions and changes

### Operation Modes

#### SIMPLE MODE (< 3 criteria)

- Workflow: `<work>` `<quality>`
- Log: Compact format (3-5 lines)
- Tokens: ~50-80

#### COMPLEX MODE (≥ 3 criteria)

- Workflow: Preparation → Hypothesis → Work → Quality → Reflection
- Log: Complete format with all sections
- Tokens: ~200-300

## WORKFLOW

You MUST follow this structured process:

### 1. PREPARATION (Planning)

```markdown
<preparation>
To complete the above task, start by writing a comprehensive planing on what changes need to be made:
- Write your general assumption on how to achieve the goal and solve the problem.
- Write multistep plan explaining your next moves.
</preparation>
```

### 2. HYPOTHESIS (Hypotheses)

```markdown
<hypothesis>
When dealing with a problem, start by writing your thoughts about the problem:
- Write at minimum 3 hypotheses on why this is happening.
- Pick the best one and attempt to implement.
</hypothesis>
```

### 3. WORK (Implementation)

```markdown
<work>
Implement changes in the best and most elegant way possible, don't let linter errors or import annoyances grab your attention in this moment, you can fix them afterward.
</work>
```

### 4. QUALITY (Quality)

```markdown
<quality>
After you implement the required changes, look for potential linter and syntax problems. Strive for clean and idiomatic patterns. Ask yourself:
- My code looks clean and maintainable?
- My code is easy to understand?
- My code is over-engineered?
- I am creating a useless abstraction?
If any of the above is true, revise your approach.
</quality>
```

### 5. REFLECTION (Reflection)

```markdown
<reflection>
After implementing changes, decide if it was the best choice or if something else needs to be done.
- Ask yourself, did I accomplished what the user asked? If the answer is yes, finish. If the answer is maybe not... imediately review your changes and see if theres anything else to do.
</reflection>
```

### Git Control

- **NEVER** make commits automatically
- **ONLY** use `/git-commit` or `/git-pull` commands when explicitly requested
- **ALWAYS** add all modified files in `/git-commit`
- **ALWAYS** create informative and structured commit messages
- **ALWAYS** confirm before executing Git operations

### Code Standards

- **ALWAYS** follow project conventions
- **ALWAYS** run tests after changes
- **ALWAYS** check linting
- **ALWAYS** keep code clean and documented

## AVAILABLE COMMANDS

- `/update-log` - Update enterprise log (MANDATORY after each final response)
- `/git-commit` - Perform structured commit (only when requested)
- `/git-pull` - Perform pull with checks (only when requested)

## PROJECT STRUCTURE

### Allowed Files

- src/, app/, lib/, components/, pages/, tests/, docs/
- package.json, requirements.txt, README.md
- Public configuration files and logs

### PROHIBITED Files

- .env\*, secrets/, .git/, node_modules/
- Credential files, keys, certificates
- Backups, database dumps, private configurations

## ERROR HANDLING

- **ALWAYS** implement proper error handling
- **ALWAYS** log errors with sufficient context
- **NEVER** ignore errors silently
- **ALWAYS** validate inputs before processing

## VALIDATION CHECKLIST

**MANDATORY**: Execute this checklist BEFORE finishing any task.

### 📋 Security Validation

- [ ] No .env or secrets files committed
- [ ] No logs with sensitive information
- [ ] No exposure of internal endpoints
- [ ] Input validation implemented
- [ ] Data sanitization applied

This configuration ensures security, traceability and control in enterprise environment.
