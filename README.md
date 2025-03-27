# rpt

repeatedly execute a command

**NOTE**: Because `repeat` is a builtin for some shells, this tool installs as both `rpt` and `repeat`.


# To install

```sh
make clobber all
sudo make install clobber
```


# Example

Run date about once a second for 2 hours:

```sh
/usr/local/bin/rpt -s 1 120 date
```

Look at a log file, once per second, 100 times:

```sh
/usr/local/bin/rpt -s 1 100 ls -l /var/log/messages
```

Repeatedly compile a program, forever:

```sh
/usr/local/bin/rpt 0 cc prog.c -o prog
```

Use the `repeat` alias to repeatedly remove a file, one a minute, forever:

```sh
/usr/local/bin/repeat -s 60 0 rm -f /var/tmp/foo
```




# To use

```
/usr/local/bin/rpt [-h] [-v level] [-V] [-n] [-N] [-s secs] count cmd [arg ...]

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

    -n          go thru the actions, but do not run any commands (def: do the action)
    -N          do not process anything, just parse arguments (def: process something)

    -s secs     sleep seconds between commands, may be a floating point number: (def: do not sleep)

    count	    number of times to repeat command, 0 ==> repeat forever

    cmd [arg ...]   command and optional args to repeat

Exit codes:
     0         all OK
     1         some internal tool exited non-zero
     2         -h and help string printed or -V and version string printed
     3         command line error
 >= 10         internal error

repeat version: 1.1.1 2025-03-26
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/rpt/security/policy)".
