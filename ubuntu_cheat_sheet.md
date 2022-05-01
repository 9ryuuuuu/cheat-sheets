# Ubuntu cheat sheet

## Vim Setting
- Color scheme
  ```Shell
  :colorscheme [space] [Ctrl+d]
  ```

- Set color scheme
  ```Shell
  vim .vimrc

  # Write below line
  syntax on
  colorscheme koehler
  ```


## Customize ls color setting
- ls color setting
  ```Shell
  echo $LS_COLORS
  ```

  ```Shell
  dircolors
  ```

- Write to .bashrc
  ```Shell
  dircolors -b >> .bashrc
  ```

- My favorite setting(Directory to yellow label and brown background)
  ```Shell
  di=01;33;41
  ```

## Customize Bash prompt
- [Reference](https://phoenixnap.com/kb/change-bash-prompt-linux)

- Setting file
  ```Shell
  ~/.bashrc
  ```

- Refresh the BASH service to apply your changes
  ```Shell
  source ~/.bashrc
  ```

- Change temporaly
  ```Shell
  export PS1="\e[1;32m\u@\h\e[0m:\e[1;33m\W\e[0m\$ "
  ```

- My favorite setting(green and yellow)
  ```Shell
  # Write below line to ~/.bashrc
  PS1="\e[1;32m\u@\h\e[0m:\e[1;33m\W\e[0m\$ "
  ```

## After installation

- Update Package list and upgrade softwears
    ```Shell
    sudo apt update && apt upgrade
    ```
- Turn off sound bell and Turn on visual bell.
    ```Shell  
    sudo vi /etc/inputrc
    set bell-style none
    set bell-style visible
    # restart
    ```

- Turn off sound on Vim
  ```Shell
  cd /home/<name>
  vi .vimrc
  # write below line in .vimrc
  ```

  ```Shell
  set visualbell
  ```



## group
- confirm group
  ```Shell
  cat /etc/group
  ```
  
- Administer group
  ```Shell
  man gpasswd
  ```
  
- add group
  ```Shell
  sudo groupadd <group>
  ```

