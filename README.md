To use the lint enforcer pre-commit git hook:
- To install the hook, run this command once inside your repository:

<code>curl https://raw.githubusercontent.com/vincentbello/lint-enforcer/master/pre-push -o ".git/hooks/pre-push"</code>
- Move the <code>pre-commit</code> script to <code>.git/hooks/</code> in your repository
    - To open the folder, use command <code>open .git/hooks</code>
- When you push to GitHub: If the JS files validate with JSHint and the Google Closure Linter, then the push will occur. If not, the hook will prevent the push and display the errors that must be fixed.
- If you want JSHint to ignore files, put the file names in <code>.jshintignore</code>, with one file name per line. You may access the file with command <code>open .jshintignore</code> from inside your repository.


*** for GCL to ignore files, you need to add <code> -x ignored1.js,ignored2.js</code> (<code> -x </code> followed by a list of comma-separated filenames) to the <code>gjslint -r .</code> command. A way to do this is to get the contents from <code>.jshintignore</code>, parse the file names to comma-separated values, and feed them into the gjslint command. However, I am thus far unable to replace the newline characters with commas when I store the file contents in a variable. If I can figure out how to do that, the user will only have to put the names of the files to ignore in <code>.jshintignore</code>, with one filename per line, and the hook will skip them with both linters.

