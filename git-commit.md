# Enterprise Git Commit

**ATTENTION**: Execute this command ONLY when explicitly requested by the user.
**ATTENTION**: **NEVER** commit directly to "main/origin" branch, always check which branch you're modifying

## Commit Process:

1. **Check Status**:

   ```bash
   git status
   ```

2. **Add all modified files**:

   ```bash
   git add -A
   ```

3. **Show changes summary (per file only)**:

   ```bash
   git diff --staged --stat
   ```

4. **Validate Files**:

   - Confirm no sensitive files are being committed
   - Check if all files are appropriate

5. **Create Structured Commit**:
   Use conventional commit format:

   ```
   type(scope): brief description

   Detailed description explaining:
   - What was changed
   - Why it was changed
   - How it was implemented

   Closes #issue-number (if applicable)
   ```

## Allowed Commit Types:

- `feat`: new feature
- `fix`: bug fix
- `docs`: documentation
- `style`: formatting, no logic changes
- `refactor`: code refactoring
- `test`: add or fix tests
- `chore`: maintenance tasks

## Usage Example:

```bash
git add -A && git diff --staged --stat
git commit -m "feat(auth): implement JWT token validation

- Add authentication middleware
- Implement expiration verification
- Add unit tests for validation

Closes #123"
```

**IMPORTANT**:

- **ALWAYS** write in [Português-PT/BR]
- **ALWAYS** confirm with user before executing
- **NEVER** commit automatically
- **ALWAYS** use descriptive and informative messages
