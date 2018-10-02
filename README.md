## Basic Stata and Git Workflow

You can call Git from the Stata command prompt via the `shell` function. For
more information on this command checkout the help documentation.

```
help shell
```

Basically, you can run any Git command from Stata by adding `shell` before it.

For example, to initialise a Git repository in the current working directory you
would have to run:

```
shell git init .
```

Which would return something like this:

```
#> Initialized empty Git repository in /path/to/your/repo
```

You can then go on to create a `.gitignore`, stage files and commit changes.

### What are the main advantages of this way of doing things?

- You get to stay within Stata and don't have to switch back and forth between
  Git bash and/or your favorite Git client.

### What are the main disadvantages?

- No automatic text complition with the `Tab` key, as you would in Git bash.
- No syntax highlighting.
- You have to type an extra word (although granted, you could create a program).

## Here are the steps I took to create this little example

1. Create Stata project in a directory, create `README.md` file and write down 
   instructions. 
2. Initialise Git repository.
   
   ```
   shell git init .
   ```
3. Stage `README.md` and `.stpr` file and commit.
   
   ```
   shell git add README.md git-with-stata.stpr
   shell git commit -m "Initial commit :hatching_chick:"
   ```
4. Create little do file and run.
5. Stage do file and figure and commit.
   ```
   shell git add scatter*
   shell git commit -m "Add a little example script and figure"
   ```
6. Go to GitHub, create a repo with the same name, without initialising a README. 
   Then locally add origin and push.
   ```
   shell git remote add origin https://github.com/mpaulacaldas/git-with-stata.git
   shell git push --set-upstream origin master
   ```
7. Update `README.md`, stage, commit and push.
   ```
   shell git add README.md
   shell git commit -m "Update README"
   shell git push
   ```
