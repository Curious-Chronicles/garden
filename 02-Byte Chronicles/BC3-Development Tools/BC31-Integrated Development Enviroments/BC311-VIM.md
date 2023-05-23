---
index: BC311
tags: vim, ide, command-line-ide
status: Started
created: 2023-05-06 14:45
updated:  <%+ tp.file.last_modified_date("dddd Do MMMM YYYY") %>
---
Related: {{related}}
URL:
1. [Vim Basics in 8 Minutes](https://www.youtube.com/watch?v=ggSyF1SVFr4)
2. 

---

# VIM Basic

When you open any file using the vim, it dumps you in the command mode, where you can set various commands

1. Quit command
```vi
:q

# Quit without saving
:q!
```

2. Write command
```vi
# Write
:w

# Wite and quit
:wq
```

3. Set number command
```vi
:set number

## To remove a number
:set nonu
```

4. Insert command
```vi
:i

```

5. To go to command mode
```vi
press ESC in keyboard

## delete a line
dd

## delete no of lines
the number of times you press "d" will delete that many times. 

## undo
uu

## undo no of lines
the number of times you press "u", it will undo that many times.

## redo
ctrl + r 

## search text
/{search-text}

## search to next
n 

## search to previous 
shift + n 

## search and edit
get to the line and press "i"

## search and replace with confirmation
:%s/{search-text}/{replace-text}/gc 

## search and replace with automatic
:%s/{search-text}/{replace-text}/g

## delete everything in the file
:%d

## Copy a line

yy or y to copy the line

## paste a line

pp 
or
shift + p to paste the copied or deleted text before the current line.
```

