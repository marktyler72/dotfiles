# dotfiles
Linux dotfiles and various configuration files for i3, i3blocks, rofi and others.

To set up a new host do the following:
~~~
    $ cd $HOME
    $ echo 'alias dotfiles="/usr/bin/git --git-dir=$HOME/projects/dotfiles/ --work-tree=$HOME"' >> $HOME/.bashrc
    $ source ~/.bashrc
    $ echo "dotfiles" >> .gitignore
    $ git remote add origin git@github.com:marktyler72/dotfiles.git
    $ git clone --bare git@github.com:marktyler72/dotfiles.git $HOME/projects/dotfiles
    $ dotfiles checkout
    $ dotfiles config --local status.showUntrackedFiles no
~~~
