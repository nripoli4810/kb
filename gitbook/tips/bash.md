# Bash Tips & Tricks

Learn Bash [via The Bash Academy](https://www.bash.academy/)

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

```bash
while [ $# -ge 1 ]; do
    case $1 in
        -a|--argA)  LOCAL_VAR_A="$2"; shift ;;          # DESCRIPTION OF VAR A
        -b|--argB)  LOCAL_VAR_B="$2"; shift ;;          # DESCRIPTION OF VAR B
        -*)         echo Unknown option\: $1 >&2; ;;    #
    esac
    shift
done
```

Some thoughts about this approach:

* You should decide what happens when you have an unknown parameter. Your two options are to ignore the parameter or exit immediately. My approach has been to exit immediately.
* You should check the number of parameters coming into the script before this while statement. If it is one or less, output a list of the possible arguments to your script to help the end user. Remember that end user might not be you one day (or it could be you two years from now!).
