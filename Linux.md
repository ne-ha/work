Installing on Ubuntu or Debian
------------------------------
Users of Debian-based Linuxes testing and unstable can use the apt-get tool to
install gitflow from the Debian repository:

    $ apt-get install git-flow

For Debian stable, one can either use the git flow installer, or the Debian package
from unstable (it works just fine on stable too).

Installing on Archlinux
------------------------------
Users of Archlinux can use packer as a tool to get AUR packages.

    $ pacman -S gitflow-git

Installing on Fedora
------------------------------
Users of Fedora can use yum as a tool to get RPM packages.

    $ yum install gitflow

Ps.: Tested on Fedora 17 and 18.

Other Linuxes
-------------
Under other Linuxes, the easiest way to install git-flow is using Rick Osborne's
excellent git-flow installer, which can be run using the following command:

    $ wget --no-check-certificate -q -O - https://raw.github.com/nvie/gitflow/develop/contrib/gitflow-installer.sh | sudo bash