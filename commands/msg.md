Suggest a commit message for the current staged changes. **Do not commit. Do not stage. Do not run any git write commands. Output the message and stop.**

## Steps

1. **Check staged changes** with `git diff --staged`
   - If nothing is staged, run `git diff` instead and note that changes are unstaged
   - If there are no changes at all, say so and stop

2. **Determine the commit type** from the diff:
   - `feat`: new capability or command added
   - `fix`: corrects broken behaviour
   - `docs`: documentation or comments only
   - `style`: formatting, whitespace — no behaviour change
   - `refactor`: restructuring without new features or bug fixes
   - `perf`: measurable performance improvement
   - `test`: tests added or updated
   - `build`: build system or dependency changes
   - `ci`: CI config changes
   - `chore`: maintenance with no production impact
   - `revert`: reverting a previous commit

3. **Write the commit message** following this format:
   ```
   {type}: short imperative summary (max 72 chars total including prefix)

   - only include a body if the summary alone doesn't convey what changed and why
   - each bullet: one meaningful change — not a file inventory
   - max 3-4 bullets; if there are more, group related changes into one
   - omit bullets that are obvious from the summary line
   ```

4. **Output the suggested message** in a fenced code block so it's easy to copy.

## Rules
- Never run `git commit` — this command only suggests, never acts
- Never add a `Co-Authored-By` line
- Prefer a one-liner over a padded body — if the summary says it all, stop there
- Do not list every file touched; only mention files when the path itself adds meaning (e.g. a config file vs. a source file)
- Use the current conversation for context on *why* changes were made — this often determines the type and whether a body is warranted
