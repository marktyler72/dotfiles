# My Linux dotfiles and configuration
Linux dotfiles and various configuration files for i3, i3blocks, rofi and others.

To set up a new host do the following:
~~~
    $ ssh-keygen -t ed25519 -C "99153612+marktyler72@users.noreply.github.com"
    $ cat ~/.ssh/id_25519.pub
    
    Log in to Github and copy in the SSH key.
    
    $ cd $HOME
    $ echo 'alias dotfiles="/usr/bin/git --git-dir=$HOME/projects/dotfiles/ --work-tree=$HOME"' >> $HOME/.bashrc
    $ source ~/.bashrc
    $ echo "dotfiles" >> .gitignore
    $ git clone --bare git@github.com:marktyler72/dotfiles.git $HOME/projects/dotfiles
    $ dotfiles checkout
    $ dotfiles config --local status.showUntrackedFiles no
~~~
