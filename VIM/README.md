# VIM Setup

This document goes through my local setup for VIM for a simple and quick editing

## Steps
* I use [Vim Plug](https://github.com/junegunn/vim-plug) for plugin manager for Vim. To install it in Unix, run the following command

  ```zsh
  curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
      https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  ```

* The `.vimrc` file contains some tools that require manual installation
  * The `fzf` tools for [fuzzy search](https://github.com/junegunn/fzf). To install, run

    ```zsh
    git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
    ~/.fzf/install
    ```

  * The `ag` ([the_silver_searcher](https://github.com/ggreer/the_silver_searcher)) tool for search files and patterns. To install, run

    ```zsh
    sudo apt install silversearcher-ag
    ```

