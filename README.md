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
