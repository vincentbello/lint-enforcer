To use the lint enforcer pre-commit git hook:
- Move the <code>pre-commit</code> script to <code>.git/hooks/</code> in your repository
    - To open the folder, use command <code>open .git/hooks</code>
- Commit a JS file to GitHub. If it validates with JSHint and the Google Closure Linter, then it will commit. If not, the hook will prevent the commit and display the errors that must be fixed before the commit.
