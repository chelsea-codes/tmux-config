# chelsea-code's tmux Configuration
*More info on [tmux](https://github.com/tmux.)*

## Setup
1. Install tmux depending on [your platform](https://github.com/tmux/tmux/wiki/Installing).

1. Install zsh:  
    `sudo apt-get install zsh`  

    *More info on [zsh](https://www.zsh.org/).*  
    
1. Download install tmux plugin manager to your user's `.tmux` directory:  
   `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`  

   *More info on [tpm plugins](https://github.com/tmux-plugins/tpm).*

1. Create a `.tmux.conf file` in your user's home directory and paste and save the contents of `.tmux.conf` in the file.

1. Update the path to the zsh binary in the `set` command under the `default shell` comment. You can get the path by running `which zsh`.

1. Start (and name) a tmux session:  
   `tmux new -s mysession`
   
   You can leave the session with:
   `prefix+d` (`Ctrl+a+d`) or simply close the terminal application. (clicking the X of a Microsoft terminal application, for example)
   
   You can re-enter this session in the future with:  
   `tmux a -t mysession`
   
   If you happen to close a session with the `exit` command, it will be terminated and you will need to create a new session.
   
   Use the command `tmux ls` to view all available sessions.
   
   For ease of usability, I set my terminal settings to run `tmux a -t mycoolsession || tmux new -s mycoolsession` when a new terminal is opened, just incase I accidentally terminate the session or dettach it unintentionally.

1. If prompted to configure zsh, select option `(2) Populate your ~/.zshrc with...`.

1. Install oh my zsh:
   `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
   *More info on [oh my zsh](https://ohmyz.sh/)*
   
1. Set your oh my zsh theme to [one of these](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) by updating the value for `ZSH_THEME=` in your user's .zshrc file. I recommend _ for this configuration.

## Changes to Default Key Bindings
See this [cheat sheet](https://tmuxcheatsheet.com/) for default commands/key bindings.

### tmux Command Prefix
*Note: When you use the prefix with key combinations, the prefix should not be held down while entering the key combinations.*  

The default prefix for tmux commands is usually `Ctrl+b`. This configuration uses `Ctrl+a` because I find it more comfortable to use.

For ultimate comfort, remap your `CAPSLOCK` key to `ESC` on tap and `Ctrl` on hold! (tmux does not seem to allow you to do this using tmux config, so it must be done at the OS level)

### Scrolling
Scrolling should work as if you were scrolling in any other window of text in a GUI.

### Copy / Paste
This configuration allows you to hold down shift with any key combination / mouse click to escape tmux's interpretation of the action. So to copy and paste, you could hold shift while selecting the text with your mouse, and then press `SHIFT+Ctrl+C/V` to copy/paste.

### Switching tmux Windows
Switch between tabs with `prefix+LeftOrRightArrowKey`(`Ctrl+a+ArrowKey`) or `prefix+TabNumber` (`Ctrl+a+TabNumber`).

### Splitting a Window Vertically / Horizontally
Press `prefix+-` (`Ctrl+a+-`) to split horizontally or `prefix+|` (`Ctrl+a+Shift+\`) to split vertically.

### Refreshing tmux Config
Reload settings from `.tmux.conf` with `prefix+r` (`Ctrl+a+r`).

## Troubleshooting

### You got an error about plugins when starting tmux
You probably did not install tmux package manager correctly. (See step #2 [above](#setup))

### tmux automatically exits when you try to start it
The path to zsh is probably not correct in the `.tmux.conf` file. (See step #4 [above](#setup))

### Some characters are showing as question marks / squares / etc
The oh my zsh theme you are using is using characters that are incompatable with your current font. Change your terminal font settings to a font that works with your theme.

## Colors
This configuration uses [256 (Xterm)](https://www.ditig.com/256-colors-cheat-sheet) colors.
