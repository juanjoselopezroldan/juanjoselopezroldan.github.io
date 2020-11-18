---
layout: default
---

#  [](#header-1) TMOUT To Automatically Log Users Out

Linux bash shell allows you to define the TMOUT environment variable. Set TMOUT to log user out after a period of inactivity automatically. The value is defined in second.
```
export TMOUT=SECONDS
```

For example the next command will implement a 5 minute idle time-out:
```
export TMOUT=300
```

This value you can indicated en your ~/.bash_profile or /etc/profile file as follows to define a 10 minute idle time out:
```
TMOUT=600
readonly TMOUT
export TMOUT
```

Save and close the file, the readonly command is used to make variables and functions readonly. In other words, your user cannot changes the value of the variable called TMOUT. Consider this as a security feature

### How Do I Disable TMOUT?
To disable auto-logout, just set the TMOUT to zero or unset it as follows:
```
export TMOUT=0
```
or
```
unset TMOUT
```

## Conclusion

TMOUT is a bash variable to auto-logout Linux users when there isn’t any activity. When we set TMOUT value greater than zero, TMOUT is treated as the default timeout for the read command. The select command terminates if the input does not arrive after TMOUT seconds when information is coming from a terminal. In an interactive shell, the value is interpreted as the number of seconds to wait for a line of input after issuing the primary prompt. Bash termina después de esperar esa cantidad de segundos si no llega una línea completa de información.