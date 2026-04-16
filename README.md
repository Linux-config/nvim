# Neovim Configuration

A clean and functional Neovim configuration built with `lazy.nvim`, featuring LSP support, autocompletion, and fuzzy finding.

## 📦 Installation

### Prerequisites (required)

Install these before first launch:

- `neovim` (0.9+ recommended)
- `git` (required for `lazy.nvim` bootstrap + Git plugins)
- `ripgrep` (`rg`, required for Telescope `live_grep`)
- `curl` (used by `rest.nvim`)
- A C compiler for Treesitter parser builds (`gcc` or `clang`)
- `make` (recommended for build steps)

### Language Server prerequisites (for this config)

This config installs these LSPs through Mason:
`jdtls`, `ts_ls`, `eslint`, `intelephense`, `tailwindcss`, `html`, `cssls`, `clangd`, `pyright`.

Install runtimes used by those servers:

- `node` + `npm` (TypeScript/ESLint/Tailwind/CSS/HTML/Intelephense/Pyright toolchain usage)
- `java` (17+ recommended, required for `jdtls`)

> Note: `jdtls` in this config is currently set up with Linux-specific paths (`/home/angelo/.../config_linux`).
> If you are on macOS or Windows, update those paths in `lua/config/lsp.lua` before expecting Java LSP to work.

Clone this repository first:

```bash
git clone <your-repo-url> nvim-config
```

### Linux

Example install command (Debian/Ubuntu):

```bash
sudo apt update && sudo apt install -y neovim git ripgrep curl build-essential make nodejs npm openjdk-17-jdk
```

1. Back up your current Neovim config (optional):
   ```bash
   mv ~/.config/nvim ~/.config/nvim.backup
   ```
2. Copy this config into place:
   ```bash
   mkdir -p ~/.config
   cp -r nvim-config ~/.config/nvim
   ```
3. Start Neovim:
   ```bash
   nvim
   ```

### macOS

Example install command (Homebrew):

```bash
brew install neovim git ripgrep curl make node openjdk
```

1. Back up your current Neovim config (optional):
   ```bash
   mv ~/.config/nvim ~/.config/nvim.backup
   ```
2. Copy this config into place:
   ```bash
   mkdir -p ~/.config
   cp -r nvim-config ~/.config/nvim
   ```
3. Start Neovim:
   ```bash
   nvim
   ```

### Windows (PowerShell)

Install dependencies with `winget` (run PowerShell as Administrator):

```powershell
winget install Neovim.Neovim Git.Git BurntSushi.ripgrep cURL.cURL OpenJS.NodeJS.LTS Oracle.JDK.17
```

For C/C++ build tools (`clangd`/Treesitter), install either:
- Visual Studio Build Tools (C++ workload), or
- LLVM/Clang via `winget install LLVM.LLVM`

1. Back up your current config (optional):
   ```powershell
   Rename-Item "$env:LOCALAPPDATA\nvim" "nvim.backup"
   ```
2. Copy this config into place:
   ```powershell
   Copy-Item -Recurse -Force ".\nvim-config" "$env:LOCALAPPDATA\nvim"
   ```
3. Start Neovim:
   ```powershell
   nvim
   ```

## ▶️ First Run / Usage

1. Open Neovim with:
   ```bash
   nvim
   ```
2. Wait for `lazy.nvim` to install plugins automatically on first launch.
3. Run `:checkhealth` to verify dependencies.
4. Use `<leader>e` to open the file tree and `<leader>f` to find files.

## 🚀 Plugins

### Core

- **[lazy.nvim](https://github.com/folke/lazy.nvim)**: Plugin manager.
- **[tokyonight.nvim](https://github.com/folke/tokyonight.nvim)**: Dark colorscheme with transparent background support.
- **[lualine.nvim](https://github.com/nvim-lualine/lualine.nvim)**: Fast and customizable statusline.

### Navigation & UI

- **[nvim-tree.lua](https://github.com/nvim-tree/nvim-tree.lua)**: Sidebar file explorer.
- **[telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)**: Highly extendable fuzzy finder.
- **[indent-blankline.nvim](https://github.com/lukas-reineke/indent-blankline.nvim)**: Adds indentation guides to all lines.
- **[nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)**: Advanced syntax highlighting and indentation.

### LSP & Autocompletion

- **[lsp-zero.nvim](https://github.com/VonHeikemen/lsp-zero.nvim)**: Simplifies LSP configuration.
- **[mason.nvim](https://github.com/williamboman/mason.nvim)**: Portable package manager for LSP servers, DAP servers, linters, and formatters.
- **[nvim-cmp](https://github.com/hrsh7th/nvim-cmp)**: Completion engine with support for LSP, snippets, and paths.
- **[LuaSnip](https://github.com/L3MON4D3/LuaSnip)**: Snippet engine for Neovim.

### Utilities

- **[rest.nvim](https://github.com/rest-nvim/rest.nvim)**: A fast Neovim HTTP client.
- **[codediff.nvim](https://github.com/esmuellert/codediff.nvim)**: VSCode-style diff rendering for checking code changes.
- **[gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim)**: Shows Git indicators in the sign column (added, changed, and removed lines).

## ⌨️ Keybindings

The leader key is set to `Space`.

### General

| Key          | Action                       |
| ------------ | ---------------------------- |
| `<leader>w`  | Save file                    |
| `<leader>q`  | Quit                         |
| `<leader>t`  | Open terminal                |
| `<leader>r`  | Run `./run.sh` in terminal   |
| `<leader>cd` | Show Code Diff (`:CodeDiff`) |

### Git / Version Control (codediff.nvim)

- `:CodeDiff` - Opens the diff viewer comparing your current file against the git index or HEAD.
- You can also compare specific branches or commits by running `:CodeDiff <revision>`.

### File Explorer (Nvim-Tree)

| Key         | Action               |
| ----------- | -------------------- |
| `<leader>e` | Toggle file explorer |

### Fuzzy Finder (Telescope)

| Key          | Action       |
| ------------ | ------------ |
| `<leader>f`  | Find files   |
| `<leader>fg` | Live grep    |
| `<leader>fb` | Find buffers |
| `<leader>fh` | Help tags    |

### LSP (lsp-zero defaults)

| Key    | Action                |
| ------ | --------------------- |
| `K`    | Hover documentation   |
| `gd`   | Go to definition      |
| `gD`   | Go to declaration     |
| `gi`   | Go to implementation  |
| `go`   | Go to type definition |
| `gr`   | Go to references      |
| `gs`   | Signature help        |
| `<F2>` | Rename symbol         |
| `<F4>` | Code action           |

### Autocompletion (nvim-cmp)

| Key         | Action                      |
| ----------- | --------------------------- |
| `<C-Space>` | Trigger completion          |
| `<CR>`      | Confirm selection           |
| `<C-e>`     | Abort completion            |
| `<C-f>`     | Scroll documentation (down) |
| `<C-b>`     | Scroll documentation (up)   |

## ⚙️ Custom Commands

- `:SetTabAmount <number>`: Sets `tabstop` and `shiftwidth` to the specified number.

## 📝 Features

- **Transparent UI**: Background transparency is enabled for the main editor and file tree.
- **Smart Tabs**: 4 spaces by default; 2 spaces for HTML and React files.
- **Diagnostics**: Inline virtual text enabled for LSP diagnostics.
- **Relative Numbers**: Enabled for easier vertical movement.
