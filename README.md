# My Linux dotfiles and configuration
Linux dotfiles and various configuration files for i3, i3blocks, rofi and others.

## Setup
The original dotfiles repo was created following the steps in https://harfangk.github.io/2016/09/18/manage-dotfiles-with-a-git-bare-repository.html

~~~
    $ git init --bare $HOME/projects/dotfiles
    $ echo 'alias dotfiles="/usr/bin/git --git-dir=$HOME/projects/dotfiles/ --work-tree=$HOME"' >> $HOME/.bashrc
    $ source ~/.bashrc
    $ dotfiles config --local status.showUntrackedFiles no
~~~
1. Create a git bare repository at ~/projects/dotfiles to track files.
1. Add alias setting to shell configuration file. Note how the paths for git directory and working tree are set.
1. Reload the shell setting.
1. Prevent untracked files from showing up when we call dotfiles status.

## Using to configure files
Use the aliased command from the home directory to manage files, and use git remote repo if you want to manage the files online.
~~~
    $ dotfiles status
    $ dotfiles add .bashrc
    $ dotfiles commit -m "Add bashrc"
    $ dotfiles remote add origin git@github.com:marktyler72/dotfiles.git
    $ dotfiles push origin main
~~~

## Set up a new host
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
