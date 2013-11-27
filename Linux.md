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

    $ yaourt -S gitflow-git

Installing on Fedora
------------------------------
Users of Fedora can use yum as a tool to get RPM packages.

    $ yum install gitflow

Ps.: Tested on Fedora 17, 18 and 19.

Other Linuxes
-------------
Under other Linuxes, the easiest way to install git-flow is using Rick Osborne's
excellent git-flow installer, which can be run using the following command for system-wide installation:

    $ wget --no-check-certificate -q -O - https://raw.github.com/nvie/gitflow/develop/contrib/gitflow-installer.sh | sudo bash

For user installation, for example in ```~/bin```,

    $ curl -O https://raw.github.com/nvie/gitflow/develop/contrib/gitflow-installer.sh
    $ chmod u+x gitflow-installer.sh
    $ INSTALL_PREFIX=~/bin ./gitflow-installer.sh

And if the installation directory (here, ```~/bin```) is in the user's path, git will find the git-flow extensions.