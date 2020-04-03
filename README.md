# Bash startup scripts

### On CUBIC
Clone this repository and set your `~/.bashrc` to
```
if [ -f /etc/bashrc ]; then
   . /etc/bashrc
fi

if [ "X$SBIABASHRC" != "Xyes" -a -f /cbica/software/lab/etc/bashrc.sbia ] ; then
	# if we have NOT already sourced the SBIA bashrc...then do so
	. /cbica/software/lab/etc/bashrc.sbia
fi

if [ -f $HOME/repos/bash/.bashrc ]; then
        source $HOME/repos/bash/.bashrc
fi
```
where `$HOME/repos/bash` is the location you cloned the repository to. And then tell your `~/.bash_profile` to simply use your `~/.bashrc`:
```
if [ -f $HOME/.bashrc ]; then
        source $HOME/.bashrc
fi
```