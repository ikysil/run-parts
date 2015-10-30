# run-parts
Bash-based implementation of `run-parts` - concept taken from
[Debian](http://www.unix.com/man-page/linux/8/run-parts/)

# Usage

    NAME
           run-parts - run scripts or programs in a directory

    SYNOPSIS
           run-parts  [--test]  [--verbose]  [--report]  [--umask=umask]
           [--arg=argument] [--exit-on-error] [--help] [--list] [--reverse]  [--]  DIRECTORY

    DESCRIPTION
           run-parts runs all the executable files named within constraints described below, found in
           directory directory.  Other files and directories are silently ignored.

           Files  are  run	in  the  lexical sort order of their names unless the --reverse option is
           given, in which case they are run in the opposite order.

    OPTIONS
           --test print the names of the scripts which would be run, but don't actually run them.

           --list print the names of the all matching files (not limited to executables),  but  don't
              actually run them. This option cannot be used with --test.

           -v, --verbose
              print the name of each script to stderr before running.

           --report
              similar  to  --verbose,  but  only prints the name of scripts which produce output.
              The script's name is printed to whichever of stdout or stderr the script produces
              output on. The script's name is not printed to stderr if --verbose also specified.

           --reverse
              reverse the scripts' execution order.

           --exit-on-error
              exit as soon as a script returns with a non-zero exit code.

           --umask=umask
              sets  the  umask to umask before running the scripts.  umask should be specified in
              octal.  By default the umask is set to 022.

           -a, --arg=argument
              pass argument to the scripts.  Use --arg once for each argument you want passed.

           --     specifies that this is the end of the options.  Any filename after -- will  be  not
              be interpreted as an option even if it starts with a hyphen.

           -h, --help
              display usage information and exit.
