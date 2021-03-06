# pkglists
Lists of the packages and software installed in my Arch Linux setup.
They separate packages installed from pacman, aur, or git repos.
There are lists containing all programs installed and some with just ricing-related stuff.


## Installing
You can automate the installation of a whole list by the commands listed below.

Aur commands make use of `yaourt`, but you can probably adapt it to other helpers.

Git repos are listed with `git clone` commands, and can be automated using stuff like myrepos (not covered here).


### Install pacman lists
`cat /home/jcarneiro/pkglists/pacman_all.lst | sudo xargs pacman -S --needed`


### Install aur lists
`cat /home/jcarneiro/pkglists/aur_all.lst | xargs yaourt -S --needed`


## Generating
To retrieve all packages explicitly installed through pacman:

`pacman -Qqe | grep -v "$(pacman -Qqm)" > pacman_all.lst`


To retrieve foreign packages (usually AUR):

`pacman -Qqm > aur_all.lst`


Ricing and git lists are maintained manually.
