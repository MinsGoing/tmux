# tmux

A comprehensive tmux configuration file with sensible defaults and useful key bindings.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/MinsGoing/tmux.git
   ```

2. Copy or symlink the configuration file to your home directory:
   ```bash
   cp .tmux.conf ~/.tmux.conf
   # or
   ln -s $(pwd)/.tmux.conf ~/.tmux.conf
   ```

3. Reload tmux configuration:
   ```bash
   tmux source-file ~/.tmux.conf
   # or press prefix + r inside tmux
   ```

## Features

### General Settings
- **Prefix key**: Changed to `Ctrl+a` (instead of default `Ctrl+b`)
- **Mouse support**: Enabled for easier pane/window management
- **Window numbering**: Starts at 1 (instead of 0) for easier keyboard access
- **Scrollback buffer**: Increased to 10,000 lines
- **256 color support**: Enabled with true color support
- **Fast escape time**: Reduced to 0ms for better vim/neovim experience

### Key Bindings

#### Window & Pane Management
- `prefix + |` - Split pane horizontally
- `prefix + -` - Split pane vertically
- `prefix + c` - Create new window (in current path)
- `prefix + r` - Reload configuration file

#### Pane Navigation
- `Alt + Arrow Keys` - Switch between panes without prefix
- `prefix + h/j/k/l` - Vim-style pane navigation (left/down/up/right)
- `prefix + H/J/K/L` - Resize panes (vim-style)

#### Window Navigation
- `prefix + Ctrl+h` - Previous window
- `prefix + Ctrl+l` - Next window

#### Copy Mode
- `prefix + Escape` - Enter copy mode
- `v` - Begin selection (in copy mode)
- `y` - Copy selection (in copy mode)
- `Ctrl+v` - Rectangle selection toggle (in copy mode)
- Uses vim keybindings in copy mode

### Status Bar
- Custom status bar with session name, date, and time
- Shows current window in bold with distinct colors
- Activity monitoring enabled for windows

## Customization

Feel free to modify `.tmux.conf` to suit your preferences. Common customizations include:
- Changing the prefix key
- Adjusting colors
- Adding plugins (consider using [TPM - Tmux Plugin Manager](https://github.com/tmux-plugins/tpm))
- Modifying key bindings

## Requirements

- tmux version 2.1 or higher (recommended: 3.0+)

## Tips

1. To see all current key bindings, press `prefix + ?`
2. To detach from a session, press `prefix + d`
3. To list all sessions: `tmux ls`
4. To attach to a session: `tmux attach -t session_name`

## License

This configuration is provided as-is for personal use.