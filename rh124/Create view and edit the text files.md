
# Using vi or vim Editor


## Creating and Editing a File.

### Open vi/vim editor

```
vi filename.txt
```

```
vim filename.txt
```

### vi/vim editor commands:

- Normal mode: Default mode for navigating and manipulating text.
- Insert mode: For inserting text (`i` to enter).
- Visual mode: For selecting text (`v` to enter character-wise, `V` for line-wise).

### Copy (yank):

- `yy` Yank (copy) a line.
- `yw` Yank a word.

### Cut (delete):

- `dd` Delete (cut) a line.
- `dw` Delete a word.

### Paste:

- `P` Paste after the cursor.
- `p` Paste before the cursor.

### Undo:

- `u` Undo the last change.
- `Ctrl + r` Redo the undone change.

### Find:

- `/pattern` Search for pattern.
- `n` Move to the next match.
- `N` Move to the previous match.

### Replace:

 - `:%s/old/new`  Replace all occurrences of old with new in the file.
 - `:s/old/new` Replace all occurrences of old with new in the current line

 ### Selecting All:

 - `ggVG` Select the entire content of the file.
 
