## Customize Windows Terminal

- Install Oh My Posh

````shell
winget install JanDeDobbeleer.OhMyPosh -s winget
````

- Remove the start text message:
    1. Go to Windows Terminal Settings.
    2. In Settings search for powershell.exe.
    3. After the powershell.exe add -nologo argument.
    4. Save setting and restart terminal.


- Gruvbox Dark color scheme for the new Windows Terminal

  ```json
    {
      "background" : "#282828",
      "black" : "#282828",
      "blue" : "#458588",
      "brightBlack" : "#928374",
      "brightBlue" : "#83A598",
      "brightCyan" : "#8EC07C",
      "brightGreen" : "#B8BB26",
      "brightPurple" : "#D3869B",
      "brightRed" : "#FB4934",
      "brightWhite" : "#EBDBB2",
      "brightYellow" : "#FABD2F",
      "cyan" : "#689D6A",
      "foreground" : "#EBDBB2",
      "green" : "#98971A",
      "name" : "Gruvbox Dark",
      "purple" : "#B16286",
      "red" : "#CC241D",
      "white" : "#A89984",
      "yellow" : "#D79921"
    }
    ```


- Install and load Terminal-Icons

  ```shell
    Install-Module -Name Terminal-Icons -Repository PSGallery  
    Import-Module Terminal-Icons
    ```

## Install Z shell (zsh) on Ubuntu WSL

- Update and upgrade packages

```shell
sudo apt update
sudo apt upgrade
```

- Install Zsh

```shell
sudo apt install zsh
```

- Set zsh as your default shell

```shell
chsh -s /bin/zsh
```

- Install oh-my-zsh

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Install Powerlevel10k

```shell
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
```

- Install zsh-autosuggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- Install zsh-completions

```shell
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions
```

Add it to `FPATH` in your `.zshrc by adding the following line before ``source "$ZSH/oh-my-zsh.sh"`` :

```shell
fpath+=${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions/src
```

- Install syntax highlighting

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Install zsh-vi-mode

```shell
git clone https://github.com/jeffreytse/zsh-vi-mode \
  $ZSH_CUSTOM/plugins/zsh-vi-mode
```

- Install you-should-use

```shell
git clone https://github.com/MichaelAquilina/zsh-you-should-use.git $ZSH_CUSTOM/plugins/you-should-use
```

- Install Colorls

```shell
sudo apt install ruby ruby-dev ruby-colorize
sudo apt install build-essential
sudo apt install libncurses5-dev
sudo gem install colorls
```

- Enable tab completion for flags

```shell
source $(dirname $(gem which colorls))/tab_complete.sh
```

Check if the ~/.config/colorls directory exists. If it doesn't exist, create it using the following command:

```shell
mkdir -p ~/.config/colorls
```

and then

```shell
cp $(dirname $(gem which colorls))/yaml/dark_colors.yaml ~/.config/colorls/dark_colors.yaml
```

in the ~/.config/colorls/dark_colors.yaml file, change the colors

```shell
# Change only main colors
unrecognized_file: '#a89984' # gold -> gray
recognized_file:   '#d79921' # yellow
executable_file:   '#98971a' # lime -> green
dir:               '#458588' # dodgerblue -> blue
```

