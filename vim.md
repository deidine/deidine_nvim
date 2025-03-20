# My Vim Research and Notes

This document contains notes and observations on using Vim, covering various commands and functionalities.  It's divided into sections: "My Research," which are my own discoveries and specific use cases, and "Others," which includes a broader compilation of common and useful Vim commands.  Finally, there's a section with VS Code Vim plugin configurations.

## My Research

This section details my personal exploration and understanding of Vim commands.

1. `0` and `^`: Go to the beginning of the line.
2. `$`: Goes to the end of the line.
3. `0`: Goes to the beginning of a word. `w`: Moves to the next word. `e`: Moves to the end of the word.
4. `d$`: Deletes the entire line; `cc` and `dd` also delete lines; `x`: cuts one character. `dw`: deletes a single word; `3d`: deletes 3 lines.
5. `f "the char you want"`: Goes to a specific character in the line.  Use `;` for forward and `,` for backward to find subsequent occurrences.
   * `F "the char you want"`: Goes *backwards* to a specific character in the line.
6. `t "the char you want"`: Goes *until* a specific character in the line (positioning the cursor just before the character).
   * `T "the char you want"`: Goes *backwards until* a specific character in the line.
7. `b`: Moves back in the word.
8. `e`: Moves forward to the end of the word; `w` moves forward to the *next* word's beginning.
9. `d + f "the char you want"`: Deletes all the characters *up to and including* the specified character.
10. `y + f "the char you want"`: Copies all the characters *up to and including* the specified character.
11. `p`: Pastes.
12. `v + f "the char you want"`: Selects all the characters *up to and including* the specified character (visual character mode).
    * `V + y`: Copies the entire *line* (visual line mode). Pasting (`p`) in visual line mode will create a new line.
13. `v + e`: In visual mode, selects to the end of the current word.  Repeated `e` presses extend the selection to the end of subsequent words.
14. `h`: Moves back one character.
15. `l`: Moves forward one character.
16. `a`, `A`, `o`, `O`, `i`, `I`, `s`, and `S`: Enter insert mode. `a`: insert after cursor; `A`: insert at end of line; `i`: insert before cursor; `I`: insert at the beginning of the line; `o`: insert a new line below; `O`: insert a new line above; `s`: delete character and insert; `S`: delete entire line and insert.
17. `j`: Moves down one line; `k`: moves up one line; `5k`: goes 5 lines up.
18. `u`: Undoes; `Ctrl + r`: redoes.
19. `/ "search word"`: Searches forward for the specified word. `n`: goes to the next match; `N`: goes back to the previous match.
20. `R`: Enters replace mode.
21. `J`: Deletes spaces and joins the current line with the next, putting all code on one line.
22. `:w`: Saves the file without quitting.
23. `:%!fmt`: Formats the entire file using the `fmt` command (requires `fmt` to be installed and available in your system's PATH).

## Others

This section provides a more comprehensive list of common and useful Vim commands.

1. `0` and `^`: Go to the beginning of the line.
2. `$`: Go to the end of the line.
3. `w`: Move to the beginning of the next word.
4. `e`: Move to the end of the current word.
5. `b`: Move back to the beginning of the current word.
6. `( and )`: Move back or forward to the beginning of the previous or next sentence.
7. `{ and }`: Move back or forward to the beginning of the previous or next paragraph.
8. `gg`: Go to the first line of the document.
9. `G`: Go to the last line of the document.
10. `<number>G`: Go to a specific line number.
11. `H`, `M`, `L`: Move to the top, middle, or bottom of the screen respectively.
12. `fx`: Find the next occurrence of the character 'x' on the current line.
13. `tx`: Move to one character before the next occurrence of the character 'x' on the current line.
14. `F` and `T`: Similar to `f` and `t`, but in the opposite direction.
15. `Ctrl + f`: Move forward one full screen.
16. `Ctrl + b`: Move backward one full screen.
17. `Ctrl + d`: Move forward (down) half a screen.
18. `Ctrl + u`: Move backward (up) half a screen.
19. `*`: Search forward for the word under the cursor.
20. `#`: Search backward for the word under the cursor.
21. `%`: Jump to the matching parenthesis, brace, or bracket.
22. `:n`: Move to the next file in the argument list.
23. `:N`: Move to the previous file in the argument list.
24. `zz`: Center the current line in the middle of the screen.
25. `zt`: Move the current line to the top of the screen.
26. `zb`: Move the current line to the bottom of the screen.
27. `zz`: Center the current line on the screen. (Duplicate of 24)
28. `zt`: Move the current line to the top of the screen. (Duplicate of 25)
29. `zb`: Move the current line to the bottom of the screen. (Duplicate of 26)
30. `.` (dot): Repeat the last change.
31. `u`: Undo the last change.
32. `Ctrl + r`: Redo the last undone change.
33. `:q`: Quit Vim.
34. `:w`: Save the current file.
35. `:wq` or `:x`: Save and quit.
36. `:q!`: Quit without saving.
37. `:e filename`: Open a new file named filename.
38. `:sp filename`: Split the window and edit a new file named filename.
39. `:vsp filename`: Split the window vertically and edit a new file named filename.
40. `:set number`: Show line numbers.
41. `:set nonumber`: Hide line numbers.

## VS Code Vim Plugin Configuration (settings.json)

This section contains configurations for the VS Code Vim plugin.

```json
{
    "java.debug.settings.onBuildFailureProceed": true,
    "vim.insertModeKeyBindings": [
        {
            "before": ["j", "j"],
            "after": ["<esc>"]
        }
        ,
        {
            "vim.leader": " ",
            "vim.hlsearch": true,
            "vim.useSystemClipboard": true,
            "vim.smartRelativeLine": true,
        }
    ],

    "vim.useCtrlKeys": true,

    "vim.normalModeKeyBindingsNonRecursive": [
        {
            "before": ["u"],
            "commands": ["undo"]
        },
        {
            "before": ["<C-r>"],
            "commands": ["redo"]
        },
        {
           "before": ["<"],
           "commands" : ["tab"]
        },
        {
           "before": [">"],
           "commands" : ["outdent"]
        },
        {
          "before": ["<leader>", "n"],
          "commands": ["workbench.action.toggleSidebarVisibility"]
        },
        {
          "before": ["K"],
          "commands": ["editor.action.showHover"]
        }
    ]
}
```
