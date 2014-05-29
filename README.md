To use the pre-commit git hook:
- Move the pre-commit script to .git/hooks/
    - To open the folder, use command open .git/hooks
- Commit a JS file to GitHub. If it validates with JSHint and the Google Closure Linter, then it will commit. If not, the hook will prevent the commit and display the errors that must be fixed before the commit.
