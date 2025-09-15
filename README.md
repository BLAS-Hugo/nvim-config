# Neovim Configuration

A modern Neovim configuration built on kickstart.nvim with enhanced Flutter/Dart development support and additional productivity plugins.

## Features

- **LSP Support**: Intelligent code completion, diagnostics, and navigation
- **Flutter/Dart Development**: Optimized for Flutter development with Dart LSP
- **Modern UI**: Clean interface with Telescope fuzzy finder and file explorer
- **Smart Completion**: Fast autocompletion with blink.cmp
- **Syntax Highlighting**: Tree-sitter powered syntax highlighting for 20+ languages
- **Git Integration**: Built-in Git workflow support
- **Code Formatting**: Automatic code formatting with conform.nvim
- **Extensible**: Easy to customize and extend

## Prerequisites

- **Neovim 0.10+** (tested on 0.11.4)
- **Git**
- **Node.js** (for some language servers)
- **Ripgrep** (`rg`) for fast searching
- **fd** for enhanced file finding (optional but recommended)

### macOS Installation
```bash
# Install Neovim
brew install neovim

# Install dependencies
brew install git node ripgrep fd

# For Flutter development
brew install --cask flutter
```

### Linux Installation
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install neovim git nodejs npm ripgrep fd-find

# Arch Linux
sudo pacman -S neovim git nodejs npm ripgrep fd
```

## Installation

1. **Backup existing config** (if you have one):
```bash
mv ~/.config/nvim ~/.config/nvim.backup
```

2. **Clone this repository**:
```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git ~/.config/nvim
```

3. **Start Neovim**:
```bash
nvim
```

The configuration will automatically install all plugins on first launch.

## Language Support

### Built-in Support
- **Dart/Flutter** (primary focus)
- **Lua** (Neovim configuration)
- **JavaScript/TypeScript**
- **Python**
- **Rust**
- **Go**
- **HTML/CSS/SCSS**
- **JSON/YAML**
- **Markdown**

### Adding New Languages
To add support for additional languages:

1. Install the language server via Mason:
```
:MasonInstall <language-server-name>
```

2. Add tree-sitter parser:
```
:TSInstall <language>
```

## Key Mappings

This configuration includes my personal key mappings for Flutter development and general productivity. Feel free to modify any mappings in `lua/vim-options.lua` or individual plugin files to make the configuration truly your own.

### Discovering Mappings
- Use `<Space>` as the leader key for most custom mappings
- Many plugins provide their own default mappings
- Run `:help` followed by a plugin name to see available commands and mappings

## Plugin Overview

### Core Plugins
- **[lazy.nvim](https://github.com/folke/lazy.nvim)**: Plugin manager
- **[kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim)**: Base configuration
- **[telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)**: Fuzzy finder
- **[blink.cmp](https://github.com/saghen/blink.cmp)**: Autocompletion
- **[nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)**: Syntax highlighting

### Development
- **[nvim-lspconfig](https://github.com/neovim/nvim-lspconfig)**: LSP configuration
- **[mason.nvim](https://github.com/williamboman/mason.nvim)**: LSP installer
- **[conform.nvim](https://github.com/stevearc/conform.nvim)**: Code formatting

## Customization

### Adding Plugins
Add new plugins by creating a new file in `lua/plugins/`:

```lua
-- lua/plugins/example.lua
return {
  'author/plugin-name',
  config = function()
    -- Plugin configuration
  end,
}
```

### Modifying Settings
Core Neovim settings are in `lua/vim-options.lua`. Edit this file to change:
- Editor options (tabs, spaces, line numbers)
- Key mappings
- General Neovim behavior

### Changing Colorscheme
The current colorscheme is configured in `lua/plugins/catppuccin.lua`. To switch themes:

1. Add a new colorscheme plugin file in `lua/plugins/`
2. Configure it as your default theme
3. Optionally remove or disable catppuccin

## Flutter Development

This configuration is optimized for Flutter development with:

- **Dart LSP**: Full language support with analysis server
- **Flutter snippets**: Code snippets for common Flutter patterns
- **Hot reload integration**: Quick restart capabilities
- **Import management**: Automatic import organization

### Flutter Commands
```
:FlutterRun          " Start Flutter app
:FlutterReload       " Hot reload
:FlutterRestart      " Hot restart
:FlutterQuit         " Stop Flutter app
```

## Troubleshooting

### Health Check
Run comprehensive health check:
```
:checkhealth
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This configuration is based on kickstart.nvim and follows the same MIT license.

## Acknowledgments

- [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim) for the solid foundation
- The Neovim community for excellent plugins and documentation
