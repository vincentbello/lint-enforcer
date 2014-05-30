To use the lint enforcer pre-commit git hook:
<h2>Install the hook</h2>
To install the hook, run these two commands inside your repository:

- <b><code>curl https://raw.githubusercontent.com/vincentbello/lint-enforcer/master/pre-push -o ".git/hooks/pre-push"</code></b><br>
- <b><code>chmod +x .git/hooks/pre-push</code>


When you push to GitHub: If the JS files validate with JSHint and the Google Closure Linter, then the push will occur. If not, the hook will prevent the push and display the errors that must be fixed.

<h3>Ignore files/directories</h3>
If you want the two linters to ignore files/directories, put the file names in <code>.jshintignore</code>, with one file name per line. You may access the file with command <code>open .jshintignore</code> from inside your repository.

<h4>How the linters ignore files</h4>
- JSHint naturally ignores files in <code>.jshintignore</code> (one filename per line).
- For GCL to ignore files, you need to add <code> -x ignored1.js,ignored2.js</code> (<code> -x </code> followed by a list of comma-separated file names) to the <code>gjslint -r .</code> command. The hook gets the contents from <code>.jshintignore</code>, parses the file names to comma-separated values, and feeds them into the gjslint command. Therefore, the user only has to put the names of the files to ignore in <code>.jshintignore</code>, with one filename per line, and the hook skips them with both linters.

