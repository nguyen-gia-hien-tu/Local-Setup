# VIM Setup

This document goes through my local setup for VIM for a simple and quick editing

## Steps
* I use [Vim Plug](https://github.com/junegunn/vim-plug) for plugin manager for
  Vim. To install it in Unix, run the following command

  ```zsh
  curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
      https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  ```

* The `.vimrc` file contains some tools that require manual installation
  * The `gruvbox` ([Retro groove color scheme for
    Vim](https://github.com/morhetz/gruvbox)) is used to set color scheme for
    Vim

  * The `NERDTree` ([A tree explorer plugin for
    Vim](https://github.com/preservim/nerdtree)) is used for viewing files in a
    tree view, convenient for viewing the structure of a directory

  * The `fzf` ([Command line fuzzy search](https://github.com/junegunn/fzf)) is
    used for searching files and patterns. To install independently (not for Vim
    as the Vim plugin also does that for you for Vim), run

    ```zsh
    git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
    ~/.fzf/install
    ```

  * The `fzf.vim` is a [`fzf` plugin for
    Vim](https://github.com/junegunn/fzf.vim)

  * The `ag` ([The silver
    searcher](https://github.com/ggreer/the_silver_searcher)) tool is used as
    the command for searching files and patterns with `fzf`. This tool is
    __required__ to be installed to run my `.vimrc` file properly. To install,
    run

    ```zsh
    sudo apt install silversearcher-ag
    ```

  * The `bat` ([A `cat` clone with wings](https://github.com/sharkdp/bat)) tool
    is used as a previewer for `fzf` plugin. To install it on Ubuntu, run

    ```zsh
    sudo apt install bat
    ```

    __IMPORTANT__: If you install bat this way, please note that the executable
    may be installed as `batcat` instead of `bat` (due to a name clash with
    another package). You can set up a `bat -> batcat` symlink or alias to
    prevent any issues that may come up because of this and to be consistent
    with other distributions:

    ```zsh
    mkdir -p ~/.local/bin
    ln -s /usr/bin/batcat ~/.local/bin/bat
    ```

    _NOTE_: If the above step doesn't resolve the problem and you still cannot
    use `bat` as the command, make sure that you have `~/.local/bin` in your
    `PATH` by adding `~/.local/bin` (or `$HOME/.local/bin`)to your path through
    adding the below command to your `~./bashrc` or `/.zshrc` file
    ```zsh
    export PATH=$PATH:$HOME/.local/bin
    ```

  * The `vim-airline` ([Lean & mean status/tabline for vim that's light as
    air.](https://github.com/vim-airline/vim-airline)) tool is used for
    displaying a nice statusline at the bottom of each vim window.

  * The `vim-airline-themes` ([The theme repository for
    `vim-airline`](https://github.com/vim-airline/vim-airline-themes)) is a
    repository containing themes for `vim-airline`.

  * The `jedi-vim` ([The Python autocompletion with
    VIM](https://github.com/davidhalter/jedi-vim)) is a tool for autocompletion
    in Python.

  * The `YouCompleteMe` ([A code-completion engine for
    Vim](https://github.com/ycm-core/YouCompleteMe)) is a code completion engine
    for Vim in many languages.

    __NOTE__: This tools requires quite a few steps of manual installation.
    Check out the
    [Installation](https://github.com/ycm-core/YouCompleteMe#installation)
    section for full guide. For Ubuntu, run the following commands in your
    terminal
    * Install CMake, Vim and Python
      ```zsh
      sudo apt install build-essential cmake vim-nox python3-dev
      ```
    * Install mono-complete, go, node, java and npm
      ```zsh
      sudo apt install mono-complete golang nodejs openjdk-17-jdk openjdk-17-jre npm
      ```
    * Compile YCM
      * Go to the directory where `YouCompleteMe` folder is located with
        ```zsh
        # NOTE: `cd` into the YouCompleteMe folder. Since I use Vim-Plug to manage Vim plugins and install the plugins under the `~/.vimrc/plugged` folder. I `cd` into that folder
        cd ~/.vim/plugged/YouCompleteMe
        ```
      * Run the Python script to install
        ```zsh
        python3 install.py --all
        ```

