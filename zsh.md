# Installing ZSH, Oh-My-ZSH and Powerlevel10k 
## This documentation goes through the installation process of different tools for ZSH

<br>

## ZSH
To install ZSH, follow [Install and Set Up ZSH As
Default](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#install-and-set-up-zsh-as-default)
or follow the following commands (for Ubuntu):

```bash
# Keep packages up to date
sudo apt update && sudo apt -y upgrade

# Install ZSH
sudo apt install zsh

# Verify the installation
zsh --version

# Make ZSH the default shell
chsh -s $(which zsh)
```

<br>

## Oh-My-ZSH
Install [oh-my-zsh](https://ohmyz.sh) following [Install oh-my-zsh
now](https://ohmyz.sh/#install) or the following command
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

<br>

## Powerlevel10k
Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k) following
[Installation for Oh My ZSH](https://github.com/romkatv/powerlevel10k#oh-my-zsh)
and [MesloLGS Nerd Font for
Powerlevel10k](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k)
or follow these steps:

  1. Clone the repo:
      ```bash
      git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
      ```

  2. In the `~/.zshrc` file set `ZSH_THEME="powerlevel10k/powerlevel10k"`

  3. Download and install these four ttf files:
      * [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
      * [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
      * [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
      * [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

  4. If you use VSCode as your text editor, configure `MesloLGS NF` as one of
     VSCode's fonts:

      1. Open Command Palette using `Ctrl + Shift + p` or `Cmd + Shift + p` for
         Mac
      2. Search with the word "Font" then check for the section "Editor: Font
         Family"
      3. Add `MesloLGS NF` to the existing list of fonts

<br>

## ZSH-Autosuggestions
Install [zsh-autosuggestion](https://github.com/zsh-users/zsh-autosuggestions)
following [Installation for Oh My
ZSH](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)
or follow these steps:

  1. Run the following command
      ```bash
      git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
      ```

  2. Add the plugin `zsh-autosuggestions` to the list of plugins for Oh My Zsh
     to load (inside `~/.zshrc`)
      ```bash
      plugins=( 
        # other plugins...
        zsh-autosuggestions
      )
      ```
     
<br>

## ZSH Syntax Highlighting
Install
[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
following [Installation for Oh My
ZSH](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)
or follow these steps:

  1. Run the following command
      ```bash
      git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
      ```

  2. Add the plugin `zsh-syntax-highlighting` to the list of plugins for Oh My
     Zsh to load (inside `~/.zshrc`)
      ```bash
      plugins=( 
        # other plugins...
        zsh-syntax-highlighting
      )
      ```

