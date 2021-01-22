## Always press <kbd>Esc</kbd>

Any instruction does not explicitly <kbd>Esc</kbd> does includes
<kbd>Esc</kbd>. 

Always press <kbd>Esc</kbd> to enter <kbd>Normal</kbd> (or Command) mode before any
commands.

## Relative number lines 

Put the following in your `~/.vimrc`:
```vi
set number           " Display line number 
set relativenumber   " Display relative line number from current
```

Or in the vi editor

First, press <kbd>Esc</kbd> to enter <kbd>Normal</kbd> mode.

```
:set number<CR>
:set relativenumber<CR>
```
> where `<CR>` is <kbd>Enter</kbd>


## How to insert text

<kbd>Insert</kbd> mode  = <kbd>Esc</kbd> + <kbd>i</kbd>

## How to copy 

Copy uses <kbd>y</kbd> (yank) operation.

In <kbd>Normal</kbd> mode, copy or yank = <kbd>y</kbd> + <kbd>Any motion</kbd>

`\n` = newline character at the end

- Always enter <kbd>Normal</kbd> mode first = Press <kbd>Esc</kbd>

- Yank the current word (excludes surrounding space) = <kbd>y</kbd> + <kbd>i</kbd> + <kbd>w</kbd>
- Yank the current word (includes surrounding space) = <kbd>y</kbd> + <kbd>a</kbd> + <kbd>w</kbd>

- Yank the current curssor until before character `x` = <kbd>y</kbd> + <kbd>t</kbd> + <kbd>x</kbd>
- Yank the current cursor until character `x`  = <kbd>y</kbd> + <kbd>f</kbd> + <kbd>x</kbd>


- Yank current line including `\n` - <kbd>y</kbd> + <kbd>y</kbd> or 

- Yank from current cusor to end of line = <kbd>y</kbd> + <kbd>$</kbd>

- Yank n lines including current line = <kbd>n</kbd> + <kbd>y</kbd> + <kbd>y</kbd>
> Yank 3 lines including current line = <kbd>3</kbd> + <kbd>y</kbd> + <kbd>y</kbd>

- Yank from current line to end of file = <kbd>y</kbd> + <kbd>G</kbd>

- Yank current line to nth current line = <kbd>y</kbd> + <kbd>n</kbd> + <kbd>G</kbd>
> Yank current line to 6th current line = <kbd>y</kbd> + <kbd>6</kbd> + <kbd>G</kbd>

## How to paste

Paste uses <kbd>p</kbd> operation

## How to delete

- Delete characters at current cursor =  <kbd>Esc</kbd> + <kbd>x</kbd>

- Delete n characters from current cursor = <kbd>Esc</kbd> + <kbd>n</kbd> + <kbd>x</kbd>
> where <kbd>n</kbd> can be any number <kbd>1</kbd>, <kbd>2</kbd>, ....,
> <kbd>n</kbd> 

- Delete 4 characters from current cursor = <kbd>Esc</kbd> + <kbd>4</kbd> + <kbd>x</kbd>

- Delete current line = <kbd>Esc</kbd> + <kbd>d</kbd> + <kbd>d</kbd>

- Delete n lines from current cursor = <kbd>Esc</kbd> + <kbd>n</kbd> + <kbd>d</kbd> + <kbd>d</kbd>

> where <kbd>n</kbd> can be any number <kbd>1</kbd>, <kbd>2</kbd>, ....,
> <kbd>n</kbd> 

- Delete current lines from end of file= <kbd>Esc</kbd> + <kbd>d</kbd> + <kbd>G</kbd>

- Delete 3 lines from current cursor = <kbd>Esc</kbd> + <kbd>3</kbd> + <kbd>d</kbd> + <kbd>d</kbd>

- Delete from current line to nth line = <kbd>Esc</kbd> + <kbd>d</kbd> + <kbd>n</kbd> + <kbd>G</kbd>
- Delete from current line to 3th line = <kbd>Esc</kbd> + <kbd>d</kbd> + <kbd>3</kbd> + <kbd>G</kbd>


## How to go to nth line

- Go to nth line = <kbd>Esc</kbd> + <kbd>n</kbd> + <kbd>G</kbd>
> where <kbd>n</kbd> can be any number <kbd>1</kbd>, <kbd>2</kbd>, ....,
> <kbd>n</kbd> 


- Go to 5th line = <kbd>Esc</kbd> + <kbd>5</kbd> + <kbd>G</kbd>

- Go to 10th line = <kbd>Esc</kbd> + <kbd>10</kbd> + <kbd>G</kbd>

## How to move to end of the line?

- Move to end of current line = <kbd>A</kbd> (or <kbd>shift</kbd> + <kbd>a</kbd>)

- Move to end of last line in file = <kbd>G</kbd> (or <kbd>shift</kbd> + <kbd>g</kbd>)

## How to insert an opening line below or after current line in vim?

- Insert new line above current line = <kbd>O</kbd> (or <kbd>shift</kbd> + <kbd>o</kbd>)

- Insert new line below current line = <kbd>o</kbd>

> The letter `O` or `o` from the word Orange. Not to be confused with zero 0. 



