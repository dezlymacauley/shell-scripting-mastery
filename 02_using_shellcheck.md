# Using `shellcheck`
_______________________________________________________________________________

### What does the `shellcheck` command do?

The `shellcheck` command is used to check for syntax errors 
in a shell script, and if that script is POSIX-compliant.

_______________________________________________________________________________

### What does `POSIX-compliant` mean?

POSIX-compliant means your shell script only uses features 
that are standard across all Unix-like systems.

Sometimes scripts may contain shell-specific syntax that only works if
that script is being run with a specific shell.

_______________________________________________________________________________

To use shellcheck do this:
```sh
shellcheck --shell=sh name-of-the-script.sh
```
_______________________________________________________________________________

