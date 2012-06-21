Installing on Mac OS X
-----------------------

Homebrew
========

If you're using [homebrew](http://github.com/mxcl/homebrew), it's simple:

    $ brew install git-flow

MacPorts
========

If you're using [MacPorts](http://macports.org/), it's simple, too:

    $ port install git-flow

If you run into problems due to Xcode 4.2 upgrades & MacPorts 2.04 with the expat dependency not installing then simply use the workaround specified in https://trac.macports.org/wiki/ProblemHotlist like so:

    $ sudo port install expat
    --->  Configuring expat
    Error: Target org.macports.configure returned: configure failure: shell command failed (see log for details)
    Log for expat is at: /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_textproc_expat/expat/main.log
    Error: Status 1 encountered during processing.
    To report a bug, see <http://guide.macports.org/#project.tickets>

    $ sudo port clean expat
    --->  Cleaning expat
    $ sudo port install expat configure.compiler=llvm-gcc-4.2
    --->  Fetching archive for expat
    --->  Attempting to fetch expat-2.1.0_0.darwin_11.x86_64.tbz2 from http://packages.macports.org/expat
    --->  Attempting to fetch expat-2.1.0_0.darwin_11.x86_64.tbz2.rmd160 from http://packages.macports.org/expat
    --->  Installing expat @2.1.0_0
    --->  Activating expat @2.1.0_0
    --->  Cleaning expat

    $ port install git-flow

wget
========

Even using wget its a one line effort.

    wget --no-check-certificate -q -O - https://github.com/nvie/gitflow/raw/develop/contrib/gitflow-installer.sh | sudo bash