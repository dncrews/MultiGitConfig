MultiGitConfig
==============

This is a simple bash function that lets you set git environments on a global scale, so that if you've pretty much got two or three you use for all of your projects and you don't want to set them all individually, you can change your global config on the fly.

Simply put this into

  ~/.git/

and create any environment directories you want. If you had two main configurations you use, you'd create two directories laid out like this:

  ~/.git/.bash_git

  ~/.git/env1/
  ~/.git/env1/.gitignore
  ~/.git/env1/.gitconfig

  ~/.git/env2/
  ~/.git/env2/.gitignore
  ~/.git/env2/.gitconfig

Then, inside your ~/.bashrc, add the following:

  if [ -f ~/.git/.bash_git ]; then
    source ~/.bash_git
  fi


At this point, either restart or simply run

  $ source ~/.bashrc


Then, to change your config, just run

  $ gitset env1


This will remove your gitconfig files and create symlinks to the ones you chose. If you choose a bad one, it will say so and not remove anything.