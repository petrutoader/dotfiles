# vladh's dotfiles

My dotfiles include configs for **vim**, **tmux**, **bash** and **zsh**. They are good for setting up Mac OS X as a development system, but work on Linux too. Here's a (non-exhaustive) list of features:

* Consistent color scheme across bash, zsh, vim etc. (custom Monokai, with alternate themes if you want them)
* Sane vim config with modern, sensible settings
* Syntax checking right inside vim with [Syntastic](https://github.com/scrooloose/syntastic)
* Fuzzy finding in vim with [ctrlp](https://github.com/kien/ctrlp.vim)
* bash & zsh prompt with git branch and time since last commit (thanks to [grb](https://github.com/garybernhardt))
* zsh [wunjo](http://www.wunjo.org/zsh-git/) support with detailed git information and assorted prompt customisations.
* powerline/airline in vim and tmux
* vim autocomplete using YouCompleteMe
* vim support for lots of things (Mustache, CoffeeScript, HAML, Jade, Markdown, Mocha, rspec, Stylus, Clojure, Processing)
* Improvements to make everything work properly in Mac OS X (e.g. clipboard in vim inside tmux)
* [z.sh](https://github.com/rupa/z) to jump around directories in bash
* Logging all bash commands to `~/.logs`

### How to use
**Make sure you have backed up your existing files!** Then, run this to clone everything into your home directory.

```bash
cd && git clone https://github.com/vladh/dotfiles --recursive && \
cd dotfiles && \
mv -i * .[^.]* ../ && \
cd && rmdir dotfiles
```

For tmux to work properly on Mac OS X, you also need to install this:

```bash
brew install reattach-to-user-namespace
```

This makes tmux open new windows in the right directory. On Mac OS, tmux may not start using the given `.tmux.conf` if `reattach-to-user-namespace` is not installed.

You also need to install YouCompleteMe if you want vim completion. [The instructions are here](https://github.com/Valloric/YouCompleteMe), but it generally goes something like:

```bash
cd ~/.vim/bundle/YouCompleteMe
./install.sh
```

To add any options you don't want to accidentally commit to the repo, like your git.config email or .bash\_profile paths, make `_private` files. These will be included in your configuration but ignored by the repo. Currently supported:

* .bash_profile_private
* .vimrc_private
* .tmux.conf_private
* .gitconfig_private
* .zshrc_private

### Credits

* [The contributors](https://github.com/vladh/dotfiles/graphs/contributors)
* [Gary Bernhardt](https://github.com/garybernhardt)
* [Steve Losh](http://stevelosh.com/)

Libraries used are difficult to list as they often change, but they are evident from the git submodules.
