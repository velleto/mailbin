# Mailbin

This is a work in progress project. It is aimed at creating some basic wrappers for an email infrastructure that uses the following technologies:

- OfflineIMAP
- IMAPFilter
- Mutt

I have written a guide to creating such an infrastructure, and these scripts are closely related. Read the guide at [dev.velleto.com](https://dev.velleto.com/2018/01/17/mutt-offlineimap-imapfilter/).

### `mailmanage`
- `rmail`. This is a routine to read mail using `Mutt`. It simply opens `mutt` with an account specific configuration file.
- `smail`. This is a routine to synchronise mail using `OfflineIMAP`. It simply calls `offlineimap` with specific accounts.
- `fmail`. This is a routine to filter mail using `IMAPFilter`. It simply calls `imapfilter`.

These used to be separate programs, however as they evolved, I realised that they were quite similar. To save lines of code, and to make them more managable, I rewrote this as one script, and based on with what name the script is called it does different things.

The idea behind `mailmanage` is to create symlinks 

    $ ln -s mailmanage rmail
    $ ln -s mailmanage smail
    $ ln -s mailmanage fmail

and then to call `rmail` to read mail, for example.

### `nmail`
This creates graphical, or terminal notifications after an `OfflineIMAP` synchronisation.
`nmailconf.py` is the corresponding configuration file.
