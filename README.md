# Neovim Configuration

This repository contains a personal Neovim configuration designed for a productive and efficient development environment. It leverages a variety of plugins and custom settings to provide features like intelligent code completion, robust language server protocol (LSP) support, a powerful fuzzy finder, and a clear, modern user interface.

## Installation

Place this file and the `lua` directory inside `~/.config/nvim`.

```bash
git clone https://github.com/your-username/your-nvim-config.git ~/.config/nvim
nvim
```
Upon the first launch, `lazy.nvim` will automatically install all necessary plugins.

## Features

This configuration provides a rich set of features to enhance the Neovim experience:

*   **Plugin Management**: Powered by [`lazy.nvim`](https://github.com/folke/lazy.nvim) for efficient and asynchronous plugin loading.
*   **File Explorer**: Integrated [`nvim-tree.lua`](https://github.com/nvim-tree/nvim-tree.lua) with `nvim-web-devicons` for a visual file system tree.
    *   **Keybind**: `<leader>e` to toggle.
*   **Fuzzy Finder**: Utilizes [`telescope.nvim`](https://github.com/nvim-telescope/telescope.nvim) for quick navigation and searching.
    *   **Keybinds**:
        *   `<leader>f`: Find files
        *   `<leader>fg`: Live grep
        *   `<leader>fb`: Find buffers
        *   `<leader>fh`: Help tags
*   **Colorscheme**: A soothing and modern "Tokyo Night" theme provided by [`folke/tokyonight.nvim`](https://github.com/folke/tokyonight.nvim).
*   **Language Server Protocol (LSP) Support**: Comprehensive LSP integration via `nvim-lspconfig`, `lsp-zero.nvim`, and `mason.nvim` for automatic language server installation and management.
*   **Autocompletion**: Advanced code completion and snippet expansion with [`nvim-cmp`](https://github.com/hrsh7th/nvim-cmp) and [`LuaSnip`](https://github.com/L3MON4D3/LuaSnip).
    *   Supports LSP, LuaSnip, file path, and buffer-based completions.
*   **Syntax Highlighting & Indentation**: Powered by [`nvim-treesitter`](https://github.com/nvim-treesitter/nvim-treesitter) for accurate syntax highlighting and smart indentation.
*   **Statusline**: A highly configurable and informative statusline provided by [`lualine.nvim`](https://github.com/nvim-lualine/lualine.nvim), featuring icons, git branch info, diagnostics, and time.
*   **Indent Guides**: Visual indentation lines provided by [`indent-blankline.nvim`](https://github.com/lukas-reineke/indent-blankline.nvim) for improved code readability.
*   **REST Client**: Integrated [`rest.nvim`](https://github.com/rest-nvim/rest.nvim) for making HTTP requests directly within Neovim.
*   **Keymaps**: Custom keybindings for frequently used actions:
    *   `<leader>t`: Open terminal
    *   `<leader>w`: Save current file
    *   `<leader>q`: Quit Neovim
    *   `<leader>r`: Run `run.sh` script in a terminal
*   **Diagnostics**: Enhanced display of LSP diagnostics with virtual text.
*   **Custom Tab Settings**:
    *   Default 4-space tabs.
    *   Custom command `:SetTabAmount <number>` to quickly change tab/shift width.
    *   Automatic 2-space tabs for `html`, `typescriptreact`, and `javascriptreact` file types.

## Supported Languages

This configuration provides robust support for a wide range of programming languages through a combination of Language Servers (LSP) and Treesitter parsers.

### Via Language Server Protocol (LSP)

The following language servers are configured for intelligent features like autocompletion, go-to-definition, refactoring, and diagnostics:

*   **Java**: `jdtls`
*   **TypeScript**: `ts_ls`, `eslint`
*   **JavaScript**: `ts_ls`, `eslint`
*   **HTML**: `html`, `tailwindcss` (for Tailwind CSS features)
*   **CSS**: `cssls`, `tailwindcss` (for Tailwind CSS features)
*   **PHP**: `intelephense`
*   **C/C++/Objective-C**: `clangd`
*   **Python**: `pyright`

### Via Treesitter

Treesitter provides advanced syntax highlighting and indentation for these languages:

*   **Markdown**
*   **Lua**
*   **Vim Script**

Additionally, specific file types like `JavaScriptReact` and `TypeScriptReact` have custom tab settings for optimal development.
 
