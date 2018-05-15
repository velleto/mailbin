Mailbin
===

This is a work in progress project. It is aimed at creating some basic wrappers for an email infrastructure that uses the following technologies:

- OfflineIMAP
- IMAPFilter
- Mutt

I have written a guide to creating such an infrastructure, and these scripts are closely related. Read the guide at [dev.velleto.com](https://dev.velleto.com/2018/01/17/mutt-offlineimap-imapfilter/).

These used to be separate programs, however as they evolved, I realised that they were quite similar. To save lines of code, and to make them more managable, I rewrote this as one script, and based on with what name the script is called it does different things.

The idea behind `mailmanage` is to create symlinks 

    $ ln -s mailmanage rmail
    $ ln -s mailmanage smail
    $ ln -s mailmanage fmail

and then to call `rmail` to read mail, for example.
