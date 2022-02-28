# chelsea-code's tmux configuration
*More info on [tmux](https://github.com/tmux.)*

# Setup
1. Install zsh:  
`sudo apt-get install zsh`  

    *More info on [zsh](https://www.zsh.org/).*  
    
1. Download install tmux plugin manager to your user's `.tmux` directory:  
`git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`  

    *More info on [tpm plugins](https://github.com/tmux-plugins/tpm).*

1. Create a `.tmux.config file` in your user's home directory and paste and save the contents of `.tmux.config` in the file.

1. Update the path to the zsh binary in the `set` command under the `default shell` comment. You can get the path by running `which zsh`.

1. Run tmux:  
`tmux`
