To use the lint enforcer pre-commit git hook:
- To install the hook, run this command once inside your repository:

<code>curl https://raw.githubusercontent.com/vincentbello/lint-enforcer/master/pre-push -o ".git/hooks/pre-push"</code>
- Move the <code>pre-commit</code> script to <code>.git/hooks/</code> in your repository
    - To open the folder, use command <code>open .git/hooks</code>
- When you push to GitHub: If the JS files validate with JSHint and the Google Closure Linter, then the push will occur. If not, the hook will prevent the push and display the errors that must be fixed.
- If you want JSHint to ignore files, put the file names in <code>.jshintignore</code>, with one file name per line. You may access the file with command <code>open .jshintignore</code> from inside your repository.

