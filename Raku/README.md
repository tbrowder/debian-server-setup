To install Raku, I use the 'rakudo-pkg' third party Debian package
installed by following the instructions found at
[Rakudo.org](https://rakudo.org/downloads/). Click on the 'Linux' tab,
then go to the bottom of the section entitled 'Binary Releases'
and click on the link 'Rakudo-Pkg package repositories'.
That should take you to [rakudo-pkg](https://nxadm.github.io/rakudo-pkg).

I pay attention to the following points to ensure a successful
installation:

+ Before executing the default curl script, I become the 'root'
  use by executing:

    $ sudo su
    #

+ Use the 'copy' button to copy the default curl script and execute
  it in the terminal window you used in the previous step.

+ Then, as root, install the package by running:

    # apt update
    # apt install rakudo-pkg

(Note those instructions are currently missing in the online text.)

+ Install 'zef' by running, as both root AND as your normal user:

    # /opt/rakudo-pkg/bin/install-zef
    
    $ /opt/rakudo-pkg/bin/install-zef

+ Set your paths for both root and yourself by adding in
  file $HOME/.bashrc a line like:

    export PATH=~/.raku/bin:$PATH
