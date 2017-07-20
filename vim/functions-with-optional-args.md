# Optional function arguments in Vim script

Functions in vim are defined like :
```vim

function! s:hello(world)
  echomsg "Hello ". a:world
endfunction

```
But I needed to be able to make the `world` parameter optional, so I could echo ___Hello world___ if the param wasn't passed but ___Hello Lanre___ if `lanre` was passed as the `world` param.

```vim
function! s:hello(...)
	let l:world = ""

	if a:0 == 1 && !empty(a:1)
		" Pick out the first args alone and see if todos need to be
		" filtered by an assignee
		let l:world = a:1
	endif

	if empty(l:world)
		echomsg "Hello ". "World"
		return
	endif

	echomsg "Hello ". l:world

```
This is extremely useful when defining commands (`command! -nargs=? Hello call hello(<f-args>`) that make use of this function. For instance 

- `:Hello` - You want this to print "Hello world"
- `:Hello adelowo` - You want this to print "Hello adelowo"

