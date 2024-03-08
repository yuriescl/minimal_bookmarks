A minimal bookmarks plugin for Neovim.

### Features

- Bookmark current line
- Edit bookmarks as a file
- Toggle bookmarks window

### Installation

#### Plugin Manager

Using [vim-plug](https://github.com/junegunn/vim-plug):

_Vimscript_:
```
call plug#begin()
...
Plug 'yuriescl/minimal-bookmarks.nvim'
...
call plug#end()
```

_Lua_:
```
vim.call('plug#begin')
...
Plug('yuriescl/minimal-bookmarks.nvim')
...
vim.call('plug#end')
```

For installation instructions using other plugin managers (e.g. [packer.nvim](https://github.com/wbthomason/packer.nvim), [lazy.nvim](https://github.com/folke/lazy.nvim)), consult your plugin manager documentation.

#### Commands

Available commands:
- `:MinimalBookmarksToggle`: Toggle bookmarks window
- `:MinimalBookmarksAdd`: Add current line to bookmarks
- `:MinimalBookmarksEdit`: Edit bookmarks file (this is the only way to edit bookmarks)
- `:MinimalBookmarksShow`: Show bookmarks window
- `:MinimalBookmarksHide`: Hide bookmarks window

#### Keybindings

By default, this plugin does not create keybindings. You can set your own keybindings in your `init.vim` or `init.lua` file.

Examples:

_Vimscript_:
```
nnoremap <silent> <leader>bb :MinimalBookmarksToggle<CR>
nnoremap <silent> <leader>be :MinimalBookmarksEdit<CR>
nnoremap <silent> <leader>ba :MinimalBookmarksAdd<CR>
```

_Lua_:
```
vim.api.nvim_set_keymap('n', '<leader>bb', ':MinimalBookmarksToggle<CR>', { noremap = true, silent = true })
vim.api.nvim_set_keymap('n', '<leader>be', ':MinimalBookmarksEdit<CR>', { noremap = true, silent = true })
vim.api.nvim_set_keymap('n', '<leader>ba', ':MinimalBookmarksAdd<CR>', { noremap = true, silent = true })
```

### Screenshots

Bookmarks window (press Enter in a bookmark to jump to it):

![image](https://github.com/yuriescl/minimal-bookmarks.nvim/assets/26092447/182bceb7-2fb3-4045-99c9-614bd7716e76)

Bookmarks file (freely edit the bookmarks database - it's a normal text file):

![image](https://github.com/yuriescl/minimal-bookmarks.nvim/assets/26092447/e037cca3-dbb9-4d15-9807-9314304fc0c6)


### FAQ

- Why not just use existing bookmark plugins like [vim-bookmarks](https://github.com/MattesGroeger/vim-bookmarks) or [bookmarks.nvim](https://github.com/tomasky/bookmarks.nvim)?
    - I tried them but found them difficult to configure, buggy and a bit bloated with unnecessary features. I just wanted something for quickly jumping to specific lines in my files. Searched for a plugin that does this, didn't find, so I wrote this one.

- Why aren't there more features?
    - With the goal of keeping this plugin minimalistic (therefore less prone to bugs, and less prone to unpredictable behavior), I decided to **not** include additional features like:
        - Per-directory bookmarks
        - Edit bookmarks inside bookmarks window
        - Line marks (e.g. bookmark sign on the line)
        - Bookmark tracking (e.g. track if bookmarked line goes up or down due to a file content change)
