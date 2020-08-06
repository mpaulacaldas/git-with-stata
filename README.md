## Basic Stata and Git Workflow

You can call Git from the Stata command prompt via the `shell` function. For
more information on this command checkout the help documentation.

```
help shell
```

Basically, you can run any Git command from Stata by typing `shell` or `!` before it.

For example, to initialise a Git repository in the current working directory you
would have to run:

```
shell git init .
```

This will launch a Shell window and close it almost immediately. Although you may think 
that nothing has changed, the git repo has been initialised. To confirm, type:

```
dir .git/
```

Which should display the contents of the hidden `.git/` directory that is present in all
git repositories.

You can then go on to create a `.gitignore`, stage files and commit changes.

### What are the main advantages of this way of doing things?

- You get to stay within Stata and don't have to switch back and forth between
  Git bash and/or your favorite Git client.

### What are the main disadvantages?

- No informative messages, that you would get by using another terminal, like Git Bash.
- No automatic text complition with the `Tab` key.
- No syntax highlighting.

## Here are the steps I took to create this little example

1. Create Stata project in a directory, create `README.md` file and write down
   instructions.
2. Initialise Git repository.

   ```
   ! git init .
   ```
3. Stage `README.md` and `.stpr` file and commit.

   ```
   ! git add README.md git-with-stata.stpr
   ! git commit -m "Initial commit :hatching_chick:"
   ```
4. Create little do file and run.
5. Stage do file and figure and commit.
   ```
   ! git add scatter*
   ! git commit -m "Add a little example script and figure"
   ```
6. Go to GitHub, create a repo with the same name, without initialising a README.
   Then locally add origin and push.
   ```
   ! git remote add origin https://github.com/mpaulacaldas/git-with-stata.git
   ! git push --set-upstream origin master
   ```
7. Update `README.md`, stage, commit and push.
   ```
   ! git add README.md
   ! git commit -m "Update README"
   ! git push
   ```
