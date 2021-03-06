VIM DJAPY CONFIGS
=================

It is VIM configurations files for comfortable work of python/django web developers. This package allows to install and configure additional plug-ins and themes.

To install additional packages need to install [vundle](https://github.com/VundleVim/Vundle.vim).

Required
--------

Only for UNIX-like platform (Linux, FreeBSD, MacOS, etc.). You need to install: `git`, `curl`, `ctags`. 


Packages
--------

Configurations include the installation of the following packages:

- [VundleVim/Vundle.vim](https://github.com/VundleVim/Vundle.vim) - is short for Vim bundle and is a Vim plugin manager;
- [valsorym/vim-nerdtree](https://github.com/valsorym/vim-nerdtree) - it is fork of [scrooloose/nerdtree](https://github.com/scrooloose/nerdtree) with fixed of some bugs (subjective approach);
- [valsorym/vim-bufexplorer](https://github.com/valsorym/vim-bufexplorer) - it is fork of [jlanzarotta/bufexplorer](https://github.com/jlanzarotta/bufexplorer) with improved display of open buffers (subjective approach);
- [valsorym/vim-tabs](https://github.com/valsorym/vim-tabs) - plugin for comfortable management of tabs;
- [matze/vim-move](https://github.com/matze/vim-move) - plugin allows you to move the text up/down without the need to cut/paste;
- [terryma/vim-multiple-cursors](https://github.com/terryma/vim-multiple-cursors) - plugin allows you to set several simultaneous cursor for text editing;
- [majutsushi/tagbar](https://github.com/majutsushi/tagbar) - plugin that provides an easy way to browse the tags of the current file and get an overview of its structure.

Quick Start
-----------

Installation of base configurations is quite simple:

```
$ git clone git://github.com/valsorym/vim-djapy-configs /tmp/vim-djapy-configs
$ cd /tmp/vim-djapy-configs
$ make install
```

Installation of additional packages
-----------------------------------

*As the package manager used [vundle](https://github.com/VundleVim/Vundle.vim) plugin. See original [documentation](https://github.com/VundleVim/Vundle.vim/blob/master/README.md) about installing additional packages*.

 1.Open config file `~/.vimrc`, find line `... custom plugins ...` and add your plugins into config file:

```
...
""" Start plugin list ...
Plugin 'VundleVim/Vundle.vim'
...
""" ... custom plugins ...

""" ADD YOUR PLUGINS HERE

""" ... end plugin list.
call vundle#end()
filetype plugin indent on
...
```

2.Restart vim, and run `:PluginInstall`. You can use others commands to:

- `:PluginList`  - lists configured plugins;
- `:PluginInstall` - installs plugins; append `!` to update or just use `:PluginUpdate`;
- `:PluginSearch foo` - searches for foo; append `!` to refresh local cache;
- `:PluginClean` - confirms removal of unused plugins; append `!` to auto-approve removal.

3.The vundle bad install the colors and syntaxes. If you have installed a new themes using vundle - they will not work in the console version of vim.  Use `:PluginUpgrade` to solve this problem.

Keyboard Shortcuts
------------------

## Main.

- `F2` - save file;
- `F8` - encoding menu;
- `F10` - open/close TagBar;
- `F12` - show/hide row numbers line;
- `C-o` - open file;
- `C-x` - remove trailing blanks;
- `C-w`, `<-` or `->` - choose window;
- `C-u` - undo (don't use just the `u` for undo);
- `C-r` - redo;
- `S-q` - reconnect the swap file - it helps when working with files through SSHFS, after crash.

... the other buttons correspond to the parameters by default.

## Tabs.

- `F4` - go to N tab;
- `C-t` - list of buffers (tabs);
- `C-n` - open new tab (or - `F7`);
- `C-h` - move tab to first position;
- `C-j` - move tab to left;
- `C-k` - move tab to right; 
- `C-l` - move tab to last position;
- `C-z` - open first tab;
- `C-PgUp` or `F5` - tab prev;
- `C-PgDw` or `F6` - tab next;

## Copy & Paste system's clipboard.

P.s. Install the `vim-gtk` package, and use `select-editor` to select the `vim-gtk` by default.

- `C-Ins` - copy text selected in visual mode (only in `gvim` or `vim-gtk`);
- `C-c`  - copy text selected in visual mode;
- `S-Ins` - paste;
- `C-v` and `C + v` (i.e. double down) - paste;
- `C-v`, `v` or `S-v` + `C-Ins` - copy text to an external clipboard;
- `S-a`, `i`, `S-r` or `r` + `S-Ins` - paste from an external clipboard.

## Flexible editing.

- `S-j` - move current line/selections down;
- `S-k` - move current line/selections up;
- `S-f` - set multiple cursor mode / the allocation of the next word under the cursor, and:
    - During the search:
        - S-b - the allocation of the previous word under the cursor;
        - S-x - ignore the current word and move on to the next;
    - After selecting all the words, you can start editing:
        - c - remove word and go into edit mode;
        - I - set the cursor in the begin of the word;
        - A - set the cursor in the end of the word.


## Vim folding commands.

- `zf#j creates a fold from the cursor down # lines;
- `zf/` - string creates a fold from the cursor to string;
- `zj` - moves the cursor to the next fold;
- `zk` - moves the cursor to the previous fold;
- `za` - toggle a fold at the cursor;
- `zo` - opens a fold at the cursor;
- `zO` - opens all folds at the cursor;
- `zc` - closes a fold under cursor;
- `zm` - increases the foldlevel by one;
- `zM` - closes all open folds;
- `zr` - decreases the foldlevel by one;
- `zR` - decreases the foldlevel to zero -- all folds will be open;
- `zd` - deletes the fold at the cursor;
- `zE` - deletes all folds;
- `[z` - move to start of open fold;
- `]z` - move to end of open fold.

## Visual block.

Click `C-v` and move arrow for select block, and click:

- `c` - to replace the contents of the block;
- `d` - to delete the content of the block;
- `S-i` - to move the cursor to the begin of the block (handy when you add spaces at the beginning of the line);
- `S-a` - to move the cursor to the end of the block;

... enter some text (the text will be written only in the one line), and click `Esc`.


## NERDTree

- `F9` - open/close NERDTree;
- `S-b` - show bookmarks;
- `C-b` - add folder to bookmarks;
- `S-d` - remove bookmark (in bookmark section);
- `S-c` - choose folder as root;
- `m` - open file manager menu.

Tab style
---------

Problem: If we have such a directory structure:

```
    myapp/
        models/
            accounts.py
            ...
        forms/
            accounts.py
            ...
        views/
            accounts.py
            ...

```

So - open this files, we have tabs (it is style `0`):

```
1. accounts.py | 2. accounts.py | 3. accounts.py
```

It is problem, because we don't know which file open on tab 2! Now we've added a tab styles. 

Set custom stule (for example - style 3):
```
echo "set tabline=%!TabName(3)" >> ~/.vimrc
```

### Style 1
Show parent folder and filename. Show only parent folder, not full path to file.
```
1. models/accounts.py | 2. forms/accounts.py | 3. views/accounts.py
```

### Style 2
Show only first and last symbol from parent folder and filename.
```
1. m..s/accounts.py | 2. f..s/accounts.py | 3. v..s/accounts.py
```

### Style 3
Show only first symbol from parent folder and filename.
```
1. m/accounts.py | 2. f/accounts.py | 3. v/accounts.py
```

But if we have files:
```
    myapp/
        models/
            accounts.py
        managers/
            accounts.py
```

Problem - `models` and `managers` starts with `m`.:
```
1. m/accounts.py | 2. m/accounts.py
```

### Style 4
Show only three first symbol from parent folder + filename. But if the name of the parent directory is less or equal to 5 characters - it is displayed as full.
```
1. mod../accounts.py | 2. forms/accounts.py | 3. views/accounts.py
```

## Tab - autonomous life
If you open 2-5 tabs - you have no problems. But if you have opened 25 tabs - it is a problem. All the tabs do not fit on the screen. Therefore, if you have more than 5 tabs open, and you begin to edit tab - the current tab automatically moves to the last position.


License
-------

Copy, modify and use in anywhere!

*Please, leave the links to the original plugins and solutions that you use in your configurations. Respect the work of other developers!*

