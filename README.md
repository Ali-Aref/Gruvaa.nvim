<div align="center">
  <h1>Gruvaa.nvim</h1>
</div>

An stand alone fork of [gruvbox.nvim](https://github.com/ellisonleao/gruvbox) in lua with [treesitter](https://github.com/nvim-treesitter/nvim-treesitter) support!
Currently it's for personal usage, but any contributions are welcome.

<h5>Images</h5>
<div>
	<img width="100%" height="auto" src="https://i.postimg.cc/mZqmJ964/gruvaa1.png" alt="gruvaa1" />
	<img width="100%" height="auto" src="https://i.postimg.cc/7hTnwBQk/gruvaa2.png" alt="gruvaa2" />
	<img width="100%" height="auto" src="https://i.postimg.cc/mr8ww1F0/gruvaa3.png" alt="gruvaa3" />
	<img width="100%" height="auto" src="https://i.postimg.cc/3RqZMM11/gruvaa4.png" alt="gruvaa4" />
	<img width="100%" height="auto" src="https://i.postimg.cc/HxntPWwj/gruvaa5.png" alt="gruvaa5" />
<div>

# Prerequisites

Neovim 0.7.0+

# Installing

Using `packer`

```lua
use { "Ali-Aref/Gruvaa.nvim" }
```

# Basic Usage

Inside `init.vim`

```vim
set background=dark " or light if you want light mode
colorscheme gruvaa
```

Inside `init.lua`

```lua
vim.o.background = "dark" -- or "light" for light mode
vim.cmd([[colorscheme gruvaa]])
```

# Configuration

Additional settings for gruvaa are:

```lua
-- setup must be called before loading the colorscheme
-- Default options:
require("gruvaa").setup({
  undercurl = true,
  underline = true,
  bold = true,
  italic = true,
  strikethrough = true,
  invert_selection = false,
  invert_signs = false,
  invert_tabline = false,
  invert_intend_guides = false,
  inverse = true, -- invert background for search, diffs, statuslines and errors
  contrast = "hard", -- can be "hard", "soft" or empty string
  overrides = {},
  dim_inactive = false,
  transparent_mode = false,
})
vim.cmd("colorscheme gruvaa")
```

## Overriding Highlight groups

If you don't enjoy the current color for a specific highlight group, now you can just override it in the setup. For
example:

```lua
require("gruvaa").setup({
    overrides = {
        SignColumn = {bg = "#ff9900"}
    }
})
vim.cmd("colorscheme gruvaa")
```

Please note that the override values must follow the attributes from the highlight group map, such as:

- **fg** - foreground color
- **bg** - background color
- **bold** - true or false for bold font
- **italic** - true or false for italic font

Other values can be seen in `:h synIDattr`
