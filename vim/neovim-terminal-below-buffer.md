### Open the terminal in Neovim in the current buffer rather than a new tab

Neovim has an inbuilt terminal which is cool but it "overshadows" the buffer and you have to `exit` + hit the <Enter> key before returning to the buffer. I installed `fzf.vim` this morning and i saw it had the fuzzy finder overlaying the statusline. I then sort out to implement something like that..

Add the following into your `~/.config/nvim/init.vim` file :


```vim

nnoremap <Leader>te :below 15sp term://$SHELL<cr>i

```
Then display the terminal with `,te` assuming `,` is set as `<Leader>`

> Even with this, I still find it preferable running a drop down terminal since I have a ___global mapping___ for it.. I make use of the quake mode in Tilix for the drop down terminal.


