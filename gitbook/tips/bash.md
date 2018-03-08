# Bash Tips & Tricks

## Check if a file exists

If you want to check if a file does not exist, insert a `!` in front of the -f.

```bash
if [ -f $PATH_TO_FILE ]; then
    echo "File exists!"
fi
```

## Passing more than 9 arguments to a script

If you're passing more than 9 arguments, then you might want to reconsider what your script is actually doing.

But, if not...

// TODO
