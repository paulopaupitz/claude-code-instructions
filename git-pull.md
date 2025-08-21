# Enterprise Git Pull

**ATTENTION**: Execute this command ONLY when explicitly requested by the user.

## Safe Pull Process:

1. **Check Local Status**:

   ```bash
   git status
   ```

2. **Check Current Branch**:

   ```bash
   git branch --show-current
   ```

3. **Backup Local Changes** (if any):

   ```bash
   git stash push -m "backup before pull $(date)"
   ```

4. **Check Remote**:

   ```bash
   git remote -v
   git fetch origin
   ```

5. **Show Differences**:

   ```bash
   git log HEAD..origin/$(git branch --show-current) --oneline
   ```

6. **Execute Pull**:

   ```bash
   git pull origin $(git branch --show-current)
   ```

7. **Check for Conflicts**:

   - If there are conflicts, stop and inform the user
   - List conflicted files
   - Wait for resolution instructions

8. **Restore Stash** (if applicable):
   ```bash
   git stash pop
   ```

## Security Checks:

- Confirm you're on the correct branch
- Check for important uncommitted changes
- Alert about potential conflicts
- Confirm operation success

## In Case of Problems:

1. **Merge Conflicts**:

   - List conflicted files
   - Wait for user instructions
   - DO NOT resolve automatically

2. **Network Error**:
   - Report the error
   - Suggest checking connectivity
   - Wait for retry attempt

**IMPORTANT**:

- **ALWAYS** write in [Português-PT/BR]
- **ALWAYS** confirm with user before executing
- **NEVER** do automatic pull
- **ALWAYS** report operation status
