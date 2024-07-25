# VIM

## Philosophy of Vim
- vim is a modal editor
- vim's interface itself is a programming language
- avoids using the mouse and the arrow keys

## Modal editing
- Different types of operating modes
    - Normal: for moving around a file and making edits
    - Insert: for inserting text
    - Replace: for replacing text
    - Visual: for selecting blocks of text
    - Command-line: for running a command
- shows the current mode in the bottom left (generally use normal and insert mode)


## Commands
- Changing modes (can rebind key)
    - `<ESC>+i`: enter insert mode
    - `<ESC>+R`: enter replace mode
    - `<ESC>+v`: enter visual mode
    - `<ESC>+V`: enter visual line mode
    - `<ESC>+<Ctrl+v>`: enter visual block mode
    - `<ESC>+:`: enter command-line mode

### Command-line
- `:q`: quit (close window)
- `:w`: save ("write")
- `:wq`: save and quit
- `:e {name of file}`: open file for editing
- `:ls`: show open buffers
- `:help {topic}`: open help
- `:sp`: create two different windows

### Movement
- `h`, `j`, `k`, `l`: left, down, up, right
- words:
    - `w`: moves to the start of the next word
    - `b`: moves backward by one word
    - `e`: end of the word
- lines:
    - `0`: beginning of the line
    - `$`: moves to the end of the line
    - `^`: first non-blank character
- screen:
    - `H`: top of screen
    - `M`: middle of screen
    - `L`: bottom of screen
- scroll:
    - `Ctrl-u`: scroll up
    - `Ctrl-d`: scroll down
- file:
    - `gg`: beginning of file
    - `G`: end of file
- find:
    - `f{character}`: moves to the first instance of that `character`
    - `F{character}`: moves to the first instance backwards of that `character`
    - `t{character}`: moves to the character right before the `character`
    - `T{character}`: moves to the chracter right after the `character`
- search:
    - `:set ic`: set the ignore case option
    - `:set hls is`: set the highlighting option
    - `:set noic`: disable ignoring case enter
    - `:nohlsearch`: remove the highlighting of matches enter

### Edits
- `o`: enters to new line and changes to insert mode 
- `O`: enters a new line above and changes to insert mode
- `d{motion}`: delete
    - `dw`: delete a word
    - `de`: delete to end of word starting at the cursor
    - `d$`: delete to end of line
    - `d0`: delete to beginning of line
    - `dd`: deletes the line
- `c{motion}`: change (similar to delete) and move to insert mode
    - `cw`: change word
    - `cc`: deletes the line but changes to insert mode
- `x`: deletes character on the cursor (equal to `dl`)
- `s`: substitute character (equal to `cl`)
- `r{character}`: replaces the character with `character`
- `u`: undo
- `Ctrl+r`: redo
- `y`: copy (`d` also copies)
    - `yy`: copies the current line
    - `yw`: copies the word
- `p`: paste
- `~`: flips the case of a character
- To copy a bunch of lines go to visual mode and then you can use the movement keys to copy
- `/{search}`: search for the word and press `enter` to move the cursor to the beginning of the word
- `/range`: searches for the word `range`
- `.`: repeats the previous editing command

### Counts
- Use a number with a letter
    - `3w`: moves 3 words forward
    - `5j`: moves 5 lines down
    - `7dw`: deletes 7 words

### Modifiers
- use modifiers to change the meaning of a noun
- `i`: inner or inside
    - `ci(`: change the contents inside the current pair of parentheses
    - `ci[`: change the contents inside the current pair of square brackets
- `a`: around
    - `da'`: delete a single-quoted string, including the surrounding single quotes