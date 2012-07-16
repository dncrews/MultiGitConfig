MultiGitConfig
==============

This is a simple bash function that lets you set git environments on a global scale, so that if you've pretty much got two or three you use for all of your projects and you don't want to set them all individually, you can change your global config on the fly.

Simply put this into

<pre>
  ~/.git/
</pre>

and create any environment directories you want. If you had two main configurations you use, you'd create two directories laid out like this:

<pre>
  ~/.git/.bash_git

  ~/.git/env1/
  ~/.git/env1/.gitignore
  ~/.git/env1/.gitconfig

  ~/.git/env2/
  ~/.git/env2/.gitignore
  ~/.git/env2/.gitconfig
</pre>

Then, inside your ~/.bashrc, add the following:

<pre>
  if [ -f ~/.git/.bash_git ]; then
    source ~/.bash_git
  fi
</pre>


At this point, either restart or simply run

<pre>
  $ source ~/.bashrc
</pre>


Then, to change your config, just run

<pre>
  $ gitset env1
</pre>


This will remove your gitconfig files and create symlinks to the ones you chose. If you choose a bad one, it will say so and not remove anything.