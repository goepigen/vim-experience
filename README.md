# My Journey Learning Vim

## 2.5h

I am 2.5 hours into my journey learning vim. I intend for this document to be written as I progress, letting the reader know the vim-related things I have been reading, learning, and working on. Before starting a did a quick google search for things like "how many hours does it take to become an expert at vim". I hope this document can contribute to answering this question.

Here is what I have done so far, written as a to-do list

1. Complete the seven vimtutor lessons.
2. Start reading the book "Practical Vim" by Drew Neil.
3. Have a [vim cheatsheet](https://vim.rtorr.com/) in a tab (or printed out) for commands that are useful but don't appear immediately or at all in vimtutor (for example, how to navigate up and down in a document by paragraph or page instead of by line)
4. Commit to using vim for all text editing tasks (programming, writing documentation such as this current one, editing config files, etc)
5. Set your terminal to use vi. This means adding the code `set -o vi` to a file like ~/bash_profile. Here are some links about this
6. Add newly learned commands to a spaced repetition app (Anki) and periodically review them. 

[StackOverflow: Is it possible to use vim keybindings in iterm2?](https://superuser.com/questions/1360220/is-it-possible-to-use-vim-key-bindings-in-iterm2)
[Unix&Linux StackExchange: Advantags of using set -o vi](https://unix.stackexchange.com/questions/30454/advantages-of-using-set-o-vi/30455#30455?newreg=dd568e4016bf455a8a5bd0d32ff86801)

6. **Every** time you don't know how to do something, google it and incorporate the solution into your vim workflow (the first step is to add it to Anki)

Here are some things I have searched for in the course of writing the initial portion of this document (ie, 2.5 hours in)

- [How to delete backwards](https://stackoverflow.com/questions/1373841/vim-deleting-backward-tricks)
- [Delete word after or around cursor in vim](https://stackoverflow.com/questions/833838/delete-word-after-or-around-cursor-in-vim)

In the course of writing the above text, I can tell you that the commands that I am using at this stage are

- Of course, `h,j,k,l`
- `$` to move to the last character on a line
- `0` to move to the first character on a line
- `a`, `A`, and `i` to go into INSERT mode after the cursor position, after the last character on the current line, and at the cursor position, respectively
- `x` to delete the character at the cursor position
- `dd` to delete an entire line
- `o` and `O` to insert a new line before the current line and after the current line, respectively, and go into INSERT mode
- `gg` and `G` to go, respectively, to the first character on the first line and the first character on the last line in the document
- `.` operator repeats the last command (this command is actually way more complex, but for now it lets me do something like `db` to delete the word before the cursor and then `.` to keep deleting more words. 
- `ce` to delete from the cursor position to the end of the word
- `f` plus a character in NORMAL mode finds the first occurrence of character to the right of the cursor on the same line.
- 'F' plus a character in NORMAL mode does the same as `f` but searching to the left.

Here are commands which I am using but only because I saw them on the internet (I don't fully understand why these commands are what they are and haven't had time to investigate yet)
- `diw`: delete entire word the cursor is on 

Here are things I notice I haven't memorized very well yet
- I confuse `j` and `k` a lot: it seems that my natural instinct is to think that `j` means up and `k` means down, but it is the opposite.
- The `ESC` key seems to far away given how important and frequent it is to go to NORMAL mode

## `.vimrc`
- At this point here is what I know about this file: it is a configuration file, you put it in your home folder (on a Mac this is `~/.vimrc`), and adding to it is an opportunity to use the vim commands learned so far. 
- I added `set number` to see line numbers.

## Here are some other interesting links I've read at this point in the journey

- [Differences between Emacs and Vim](https://stackoverflow.com/questions/1430164/differences-between-emacs-and-vim)
- [Gilles Castel: How I'm able to take notes in mathematics lectures using Latex and Vim](https://castel.dev/post/lecture-notes-1/)

This particular article is what actually made me decide to commit to learning vim. 
I was about to take notes from a Chemistry course in Google Docs. Then I thought: Latex would be better. 

So I fired up TexShop. 

Then I noticed that it wasn't a particularly efficient process writing there. So I googled something like "best vim editor for mac" and quickly stumbled on people talking about vim plugins that enable you to use latex. 

Next, I found [this youtube video](https://www.youtube.com/watch?v=DOtM1mrWjUo) of a guy called Charlie Mars who has an awesome setup for making Latex documents using vim while listening to a lecture. He said he was heavily inspired by the article by Gilles Castel, and that is how I stumbled upon that article.

## Summary

- Use vimtutor, Anki, a vim cheatsheet, the book Practical Vim, and commit to using `vim` for everything.

## 2.5 -  

The end of vimtutor has two book recommendations - **Vi IMproved** by Sam Oualline and **Learning the Vi and Vim Editors** by Linda Lamb. I started to read these books.

At this point I already have the feeling that the `ESC` key is essential but too far away from my hand position for my taste and comfort. Googling about this, it is clear this feeling is shared by many people and many remap some other key or sequence of keystrokes to `ESC`.

Apparently, on [early keyboards the layout had ESC and CTRL in easier to reach positions](https://commons.wikimedia.org/wiki/File:KB_Terminal_ADM3A.svg#/media/File:KB_Terminal_ADM3A.svg). See also [Why is the "esc" key arguably the most important key in VIM so inaccessible](https://www.reddit.com/r/vim/comments/wmtjfj/why_is_the_esc_key_arguably_the_most_important/) on reddit.

There are multiple options to address this issue. I decided to go with the simplest option for now: open System Preferences->Modifier Keys on Mac and change the action performed for the Caps Lock key to Escape. 

I also mapped the sequence of keystrokes `jk` to `ESC` to try it out (some people do this, some people use `kj` or `jj`). I did this by adding the following to my `.vimrc`: `imap jk <Esc>`.

Here are some links regarding this

[Using Caps Lock as Esc in Mac OS X](https://stackoverflow.com/questions/127591/using-caps-lock-as-esc-in-mac-os-x) 
[Using Caps Lock as Esc in Mac OS X](https://stackoverflow.com/questions/127591/using-caps-lock-as-esc-in-mac-os-x/40254864#40254864)

## I started using `:help` a bit
`:help` opens the help documentation in vim. Perhaps more useful is passing a topic about which you want help, e.g. `:help .` will get you help on the `.` operator (as used in NORMAL mode). 

To get help about a command in INSERT mode, you use a command like `:help _i_CTRL-H`, which gets you help on the `CTRL-H` command when used in INSERT mode. 
The `_i` is a prefix, and there are others.

## New commands in `NORMAL` mode
- `ZZ`, that is two capital `Z`'s, writes the file and exits.
- `(` moves to the beginning of the current sentence
- `)` moves to the beginning of the next sentence
- `{` moves to the beginning of the current paragraph 
- '}` moves to the beginning of the next paragraph
- `t[character]` works like `f[character]` but stops one character before the indicated character. E.g., `tf` searches for the character `f` to the right of the cursor, on the same line, and moves to the position right before. `T[character` mirrors `F[character]`.
- `y{motion}` copies (ie, "yanks") whatever is indicated by `motion`. For example, `yy` copies the current line, then `p` pastes it. `yw` copies to the beginning of the next word, `y$` copies the current line starting from the cursor position (excluding newline character), `yiw` copies the word the cursor is in, etc. [Here is more information](https://vim.fandom.com/wiki/Copy,_cut_and_paste#:~:text=Press%20d%20to%20cut%20(or,or%20p%20to%20paste%20after.).  
- `d` seems to actually be the operator `cut`, not `delete`.
- `"_dd` deletes a line but saves it to the "black hole register"
- `CTRL-u` and `CTRL-d` scroll up and down half a screen, respectively.
- `D` is a shortcut for `d$`
- `c` means **change**. It acts just like the `d` command but it leaves you in INSERT mode. An exception to this is `cw` and `dw`: they aren't exactly the same, but pretty close.
- `cc` deletes the entire line and goes into INSERT mode, and `C` is the same as `c$`
- `df{character}` deletes (ie, cuts) up to next `character`
- `J` joins the current line with the next one with a space added to the end of the first line 
Note that many of the topics above are rabbit holes I could get into, but at this point I'd like to trust that the books I am reading will be better at deciding the topics most useful to me at this stage, rather than drilling down into too much detail about specific things I don't know about (like registers). That being said, `:help quote` tells me that when I type in `"{register}` I am telling vim to use `register` for the next delete, and `:reg[isters]` shows me the available registers and what's on them. For now this is enough for me.
- `~` changes a character's case

## Macros
To start recording a macro on register `character` use the command `q[character]`. To stop recording, type `q`. To use the macro, use the command `:@[character]`

## Digraphs
If we ever need to display some crazy character, we can enter the command `:digraphs` to see a table of characters and the digraphs that represent them in `vim`.
A digraph is a combination of two characters that represent one character.

It seems that most of these digraphs combine `CTRL K` with something extra, like for example `sa` which gives us さ.

## Search
- `/` to start the search, then the string. After an occurrence has been found, `n` to go to the next occurrence. Can also use things like `3n` to go to the third next occurrence.
- after `/`, up and down keys go through the search history
- `:set hlsearch` turns on the highlighting of all found strings after a search
- `:nohlsearch` turns of the currently highlighted strings but keeps highlighting on for future searches
- incremental search is turned on with `:set incsearch`
- reverse search is done using the `?` command, with analogous use of `n` (next occurrence searching backwards)
- `N` searches in the opposite direction to the search direction. That is, if we are doing a forward search using `/` then `n` gets the next occurrence in the forward direction and `N` gets the next occurrence in the backward direction. If we are doing a backward search using `?` then `n` and `N` give us next occurrences in the backward and forward directions, respectively.


## Quick Tips
- When we open a help page (say, `:help quote`), for reasons I have yet to discover the screen (ie, my iTerm terminal) gets split with one half being the help page and the other half my original file. This is helpful in the sense that I can read the help pages while looking at the original file that likely prompted the need to look at the help pages. 

To switch between the two "windows" use `CTRL-w CTRL-w`.
