**The script is used to close a currently working buffer (without closing others) in Vim.**

Reference: [Deleting a buffer without closing the window](https://vim.fandom.com/wiki/Deleting_a_buffer_without_closing_the_window)

--------------------------------

### Method One

Step 1: Create a directory named `plugin` under your `.vim`

```bash
sudo mkdir ~/.vim/plugin
```

Step 2: Git clone this repo under `plugin`:
```bash
cd ~/.vim/plugin
git clone https://github.com/Jeff1999/vim-close-current-buffer.git
```

Step 3: Modify the last line of `bclose.vim` under `vim-close-current-buffer/plugin`

The default shortcut is `ctrl + ↑`, you can customize it to whatever you like.

```bash
nnoremap <silent> <C-Up> :Bclose<CR>
```

### Method Two (with `vimplus`)

`vimplus` is an automatic configuration program. More details? Click [here](https://github.com/chxuan/vimplus).

Step 1: Install `vimplus`

```bash
git clone https://github.com/chxuan/vimplus.git ~/.vimplus
cd ~/.vimplus
./install.sh
```

Step 2: Set font

Set `Droid Sans Mono Nerd Font` as your terminal font.

Step 3: Update `vimplus`

```bash
./update.sh
```

Step 4: Install this plugin

Since you have installed `vimplus`, there is a file named `~/.vimrc.custom.plugins`, where you can install your own plugins and organize them with `vimplus`.

Add this line in your `.vimrc.custom.plugins`

```
Plug 'Jeff1999/vim-close-current-buffer'
```

Then, type those commands in your Vim:

```bash
:w
,s
,,i
```

Step 5: Jump to `~/.vim/plugged/`, modify the last line of `bclose.vim` under `vim-close-current-buffer/plugin` as what we do in method one.

OR

Add a line in `~/.vimrc.custom.config`, where you can set your own configures.

```bash
nnoremap <C-Up> :Bclose<CR>
```

(I also set `ctrl + ↓` to list all buffers. After you have installed `vimplus`, there is a plugin named `vim-buffer` to let you switch between buffers, so I set `ctrl + ← / →` to switch to the previous/next buffer.)

```
nnoremap <C-Down> :buffers<CR>
nnoremap <C-Left> :PreviousBuffer<CR>
nnoremap <C-Right> :NextBuffer<CR>
```

