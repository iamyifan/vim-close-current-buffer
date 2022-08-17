## The script is used to close a currently working buffer (without closing others) in Vim.

Reference: [Deleting a buffer without closing the window](https://vim.fandom.com/wiki/Deleting_a_buffer_without_closing_the_window)

--------------------------------

### Method One (only Vim)

- Step 1: Create a directory named `plugin` under your `.vim`

  ```bash
  sudo mkdir ~/.vim/plugin
  ```

- Step 2: Git clone this repo under `plugin`:

  ```bash
  cd ~/.vim/plugin
  git clone https://github.com/Jeff1999/vim-close-current-buffer.git
  ```

- Step 3: Modify the last line of `bclose.vim` under `~/.vim/plugin/vim-close-current-buffer/plugin`

  The default shortcut is `ctrl + ↑`. Now, you can customize it to whatever you like.

  ```bash
  nnoremap <silent> <C-Up> :Bclose<CR>
  ```

### Method Two (with `vimplus`)

`vimplus` is an automatic configuration program for Vim. More details? Click [here](https://github.com/chxuan/vimplus).

- Step 1: Install `vimplus`

  ```bash
  git clone https://github.com/chxuan/vimplus.git ~/.vimplus
  cd ~/.vimplus
  ./install.sh
  ```

- Step 2: Set your terminal font

  Set `Droid Sans Mono Nerd Font` as the default terminal font.

- Step 3: Update `vimplus`

  ```bash
  ./update.sh
  ```

- Step 4: Install this plugin with `vimnplus`

  Since you have installed `vimplus`, there is a file named `~/.vimrc.custom.plugins`, where you can install your own plugins and organize them with `vimplus`. Add this line in your `.vimrc.custom.plugins`:

  ```bash
  Plug 'Jeff1999/vim-close-current-buffer'
  ```

  Then, run these commands in your Vim to install the plugin:

  ```bash
  :w
  ,s
  ,,i
  ```

- Step 5: Jump to `~/.vim/plugged/`, there should be a folder named `vim-close-current-buffer`. Modify the last line of `bclose.vim` under `vim-close-current-buffer/plugin` as what we do in method one.

  OR

  Just add a line in `~/.vimrc.custom.config`, where you can set your own configures.

  ```bash
  nnoremap <C-Up> :Bclose<CR>
  ```
  (I set `ctrl + ↓` to list all buffers. After you have installed `vimplus`, there is a plugin named `vim-buffer` to let you switch between buffers, so I also set `ctrl + ← / →` to switch to the previous/next buffer.)
  
  ```bash
  nnoremap <C-Down> :buffers<CR>
  nnoremap <C-Left> :PreviousBuffer<CR>
  nnoremap <C-Right> :NextBuffer<CR>
  ```
  
  

