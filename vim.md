### Find a word in Vim or vi text editor
To search using Vim/vi, for the current word:

<br>In normal mode, you can search forward or backward.
<br>One can search forward in vim/vi by pressing <code><mark><b style="color:red;">/</b></mark></code> and then typing your search pattern/word.
<br>To search backward in vi/vim by pressing <code><mark><b style="color:red;">?</b></mark></code> and then typing your search pattern/word.
<br>Once word found in vim, you can press the <code><mark><b style="color:red;">n</b></mark></code> key to go directly to the next occurrence of the word in backwards. Press the <code><mark><b style="color:red;">N</b></mark></code> key to go directly to the opposite direction, i.e. forwards.

reference: https://www.cyberciti.biz/faq/find-a-word-in-vim-or-vi-text-editor/


### Delete Multiple Lines
1. Press Esc.
2. Move the cursor to the first line you want to remove.
3. Use one of the following commands (replacing [#] with the number of lines):
example: 3dd
```
[numberLines]dd
```

### Use Vim
```
vim name_file
```

### Edition Vim, only use keyboard <strong>'i'</strong>, after use, keyboard <strong>ESC</strong> and <strong>:wq</strong> and <strong>ENTER</strong>
```
i
ESC
:wq
ENTER
```

### Close without save
```
ESC
:q!
```
