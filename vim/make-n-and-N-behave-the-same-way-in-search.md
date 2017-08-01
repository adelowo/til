# Normalize the behaviour of n and N while navigating through search results

There are two modes to searching text in Vim - `?` and `/`. `?` searches backwards (as in to the top of the file) while `/` forward (bottom of the file).
To cycle through results, you use `n` and `N`.
With `/`, `n` takes you forward while `N` takes you backwards. As I am new to Vim, I recently found out about `?`
and I was expecting the same behaviour of `n` and `N` when `?` is used for searching.

Boy, I was wrong. In `?` search results, `n` actually takes you backwards while `N` takes you forward.
This is plain hard [1], it takes a second to realize and make use of the correct command - `n` or `N` but I would rather prefer consistency.
So I mapped `n` and `N` to always go forward and backwards respectively regardless of the search command used - `?` or `/`.

```vim

nnoremap <expr> n  'Nn'[v:searchforward]
nnoremap <expr> N  'nN'[v:searchforward]

```


[1] : This behaviour is actually the way it is suppposed to be as `?` searches backwards, ___so the next search term has got to be backwards not forward___
