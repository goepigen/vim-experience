# My Journey Learning Vim

# 5h

I am 5 hours into my journey learning vim. I intend for this document to be written as I progress, letting the reader know the vim-related things I have been reading, learning, and working on. Before starting a did a quick google search for things like "how many hours does it take to become an expert at vim". I hope this document can contribute to answering this question.

### Here is what I have done so far, written as a to-do list

1. Complete the seven vimtutor lessons.
2. Start reading the book "Practical Vim" by Drew Neil.
3. Have a [vim cheatsheet](https://vim.rtorr.com/) in a tab (or printed out) for commands that are useful but don't appear immediately or at all in vimtutor (for example, how to navigate up and down in a document by paragraph or page instead of by line)
4. Commit to using vim for all text editing tasks (programming, writing documentation such as this current one, editing config files, etc)
5. Set your terminal to use vi. This means adding the code `set -o vi` to a file like ~/bash_profile. Here are some links about this
6. Add newly learned commands to a spaced repetition app (Anki) and periodically review them. 

[StackOverflow: Is it possible to use vim keybindings in iterm2?](https://superuser.com/questions/1360220/is-it-possible-to-use-vim-key-bindings-in-iterm2)
[Unix&Linux StackExchange: Advantags of using set -o vi](https://unix.stackexchange.com/questions/30454/advantages-of-using-set-o-vi/30455#30455?newreg=dd568e4016bf455a8a5bd0d32ff86801)

6. **Every** time you don't know how to do something, google it and incorporate the solution into your vim workflow (the first step is to add it to Anki)

### Here are some things I have searched for in the course of writing the initial portion of this document (ie, 2.5 hours in)

- [How to delete backwards](https://stackoverflow.com/questions/1373841/vim-deleting-backward-tricks)
- [Delete word after or around cursor in vim](https://stackoverflow.com/questions/833838/delete-word-after-or-around-cursor-in-vim)

### In the course of writing the above text, I can tell you that the commands that I am using at this stage are

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

### Here are commands which I am using but only because I saw them on the internet (I don't fully understand why these commands are what they are and haven't had time to investigate yet)
- `diw`: delete entire word the cursor is on 

### Here are things I notice I haven't memorized very well yet
- I confuse `j` and `k` a lot: it seems that my natural instinct is to think that `j` means up and `k` means down, but it is the opposite.
- The `ESC` key seems to far away given how important and frequent it is to go to NORMAL mode

### `.vimrc`
- At this point here is what I know about this file: it is a configuration file, you put it in your home folder (on a Mac this is `~/.vimrc`), and adding to it is an opportunity to use the vim commands learned so far. 
- I added `set number` to see line numbers.

### Here are some other interesting links I've read at this point in the journey

- [Differences between Emacs and Vim](https://stackoverflow.com/questions/1430164/differences-between-emacs-and-vim)
- [Gilles Castel: How I'm able to take notes in mathematics lectures using Latex and Vim](https://castel.dev/post/lecture-notes-1/)

This particular article is what actually made me decide to commit to learning vim. 
I was about to take notes from a Chemistry course in Google Docs. Then I thought: Latex would be better. 

So I fired up TexShop. 

Then I noticed that it wasn't a particularly efficient process writing there. So I googled something like "best vim editor for mac" and quickly stumbled on people talking about vim plugins that enable you to use latex. 

Next, I found [this youtube video](https://www.youtube.com/watch?v=DOtM1mrWjUo) of a guy called Charlie Mars who has an awesome setup for making Latex documents using vim while listening to a lecture. He said he was heavily inspired by the article by Gilles Castel, and that is how I stumbled upon that article.

### Summary

- Use vimtutor, Anki, a vim cheatsheet, the book Practical Vim, and commit to using `vim` for everything.

# 10.5h 

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
- Vim uses regular expressions. 

## Quick Tips
- When we open a help page (say, `:help quote`), for reasons I have yet to discover the screen (ie, my iTerm terminal) gets split with one half being the help page and the other half my original file. This is helpful in the sense that I can read the help pages while looking at the original file that likely prompted the need to look at the help pages. 

To switch between the two "windows" use `CTRL-w CTRL-w`.

## `.vimrc` updates
- I wanted to be able to insert a blank line after the line of the cursor, keeping the cursor where it is and in NORMAL mode. I read [this StackExchange post](https://superuser.com/questions/607163/inserting-a-blank-line-in-vim) entitled **Inserting a blank line in vim?** that offered multiple solutions. I decided to go with a simple solution for now, adding the following to my `.vimrc`: 

`map <Enter> o<ESC>k`
`map <S-Enter> O<ESC>`

which allows me to obtain the desired behavior when I press `<Enter>` in NORMAL mode. `<S-Enter>` means `SHIFT` plus `ENTER`, which should add a blank line above the cursor line. This is not, however, working as of right now.

# 18h
Immediately after the 10.5h of the previous section I decided to pause my study of pure vim commands for just a bit to try to accomplish one of my initial goals which was to use snippets to write Latex (but ultimately any file type) very quickly in vim.

To that end I decided to follow [a seven-part series on using vim to write LaTeX documents using snippets](https://ejmastnak.github.io/tutorials/vim-latex/ultisnips.html).

I had to research and install a few things (reinstall vim via homebrew because the default system installation I was using didn't have `python3` enabled, `Ultisnips`, `Vundle`) but ultimately it wasn't that difficult (meaning, I followed instructions and didn't get stuck at any point).

After an hour or two I was already able to write snippets and use them in vim. 

### Editing in Multiple Windows

At this point I was editing multiple files in different iTerm tabs: `.vimrc`, the current document, one or two snippet files, and a random file used for testing stuff out. 
I knew it was possible to have multiple windows open, so I decided to jump to Chapter 5 - Windows of Oualline's book. Here is what I learned

- `:split` opens a new window below the current window (with the same file), leaving the cursor in the top window. This is useful if you want to see different parts of the same file simultaneously
- `:split path/to/file` opens the indicated file in a window above the current window and the cursor is open in this new window
- `:split +/some_string` path/to/file` also opens the file as before but executes the command `/some_string` after opening the file
- `:20split ~/.vimrc` opens the file `~/.vimrc` but limits the new window to twenty lines
- `:new` opens a new file in a new window above the current one and puts the cursor there
- to resize the current window, press `ctrl-w` and `+` to increase the size by one line, and `ctrl-w` and `-` to decrease by one line. If you use `ctrl-w` and `_` the window will be increased to the maximum size. Pehaps more useful is some variation of `ctrl-w` and `50` and `-`, which decreases the size by 50 lines
- finally, there is also `ctrl-w` and `=` which makes the windows the same size

### Buffers
- the term "buffer" describes a file being edited
- normally, if something has a window on the screen it is a buffer
- however, there are also hidden buffers. When you are on a screen and execute the command `:hide`, the current buffer becomes hidden, disappearing from the screen (but vim still knows the buffer is being edited).
- `:buffers` shows a list of buffers
- `:buffer [number]`or `[number]buffer` selects a buffer to use though it is also possible to simply specify the filename as in `:buffer [filename]`
- `sbuffer [number]` selects a buffer and splits the window to edit the new selection in the new window
- there are quite a few other commands for navigating the buffers (e.g., go to the first or last buffer in the list, go to the next buffer, etc)

### Plugins
- a plugin is the name for a Vimscript file that is loaded when you start Vim
- you can use a plugin manager to install and configure plugins. I am using `Vundle` (no specific reason other than it was the one mentioned in one of the articles I was reading first)
- I ran into a small issue while installing the plugin `lervag/vimtex`. [Part 3 of the series I am reading](https://ejmastnak.github.io/tutorials/vim-latex/ftplugin.html) talks about Vim's `ftplugin` system. That article shows us how to write a plugin that only applies to one specific type of file (it's kind of like writing a `.vimrc` that only applies to, for example, `tex` files).

The article instructs us to enable filetype detection by adding the line `filetype on` to our `.vimrc`. 

Vundle, on the other hand, has as required configuration in `.vimrc` the option `filetype off`. 

I had to keep this off while running Vundle's `PluginInstall` command (after adding the line `Plugin 'lervag/vimtex'`), and turn it on again later. 

This is an example of the mini shitstorms that make this whole ordeal somewhat hacky. But hey, we are still in the dark ages of the coming revolution.

### New Things I Learned Along the Way
- I noticed that sometimes my `delete` key didn't work. For example, in `NORMAL` mode I'd use the command `A` to go to the position right after the last character on a line and enter `INSERT` mode and immediately hit the `delete` key and it wouldn't work.

[This StackExchange question](https://vi.stackexchange.com/questions/2162/why-doesnt-the-backspace-key-work-in-insert-mode) explains why this is: `vim` has configuration for how a certain group of keys including `delete` work in different very specific situations. 
One of the specific situations is right after you enter `INSERT` mode. 

Apparently, my configuration is such that backspacing over the start of the `INSERT` position isn't permitted.  

So I added the following to my `.vimrc`: `set backspace=indent,eol,start`

### Other Impressions at this Stage
- I still confuse `j` and `k` a lot
- However, I am starting to use search functionality much more. `:set incsearch` and then `/[search term]` and then `<Enter>` is something I am using quite a bit to navigate rather than try to navigate using direction keys.

### Right at 18h
I start writing these sections as I am going through the learning process. Right now I am at exactly 17h48m. 

This whole thing is kind of like a journal. It's not meant to be a tutorial or to help you learn vim outright, but rather to give you a glimpse at what I did because I think that can be super helpful.

However, I also want to note that because I am moving through a lot of material I think I am probably forgetting some things. Let me get to the last thing I learned just now: key mappings. Some of the default sequences of commands kind of suck. 

The fact that I can customize key mappings means I can think about the best ways of accomplishing things taking into account my specific situation (the keyboard layout, the size of my hands, and just general tastes and preferences I have.

The seventh part of the seven-part series about vimtex is actually called "A Vimscript Primer for Filetyp-Specific Workflows", and it starts with a whole section about key mappings which was enough to get me started. 

Just now I decided to read Chapter 8 "Basic Abbreviations, Keyboard Mapping, and Initialization Files" from Oualline's book. So at this point I am somewhere near 18h, and will start another section recording my journey. 

# 21h

I pretty much immediately ran into a little task I didn't know how to accomplish. At 18h I decided to do a review in Anki and make sure I had added all the new com there. 
Part of the review is actually running the commands I saved in flashcards in vim. I decided to copy the current document into vim open in another tab. I realized it wasn't completely straightforward. [This is the solution I ended up going with](https://vi.stackexchange.com/questions/4600/how-to-copy-across-terminals).

### Things I Learned Along the Way
- When we do a search using `f`, `F`, `t`, or `T` we use `;` to go to the next occurrence of the thing we were searching for. 

### State of Affairs

It is now exactly 21h4min into the journey. I used 54m to review in Anki during this last stretch. 

There is a difference between learning and simply doing/executing. This whole affair of setting up vim to work with snippets, vimtex, and a pdf reader with forward and inverse search involved learning, but a lot of simply executing the steps. 

The seven-part series I've alluded to is absolutely phenomenal in terms of didactical writing and I wish all documenatation were so clear and accurate. 
At this point it is all set up. I can now take notes using Latex and it will be a journey to fill in all the gaps necessary to to be fast and efficient.

### Impressions
- Obviously, this document is getting long. I am not sure what I set out to do exactly but now I feel it is a journal to register the experience in its entirety. At points I sort of documented the actual commands' usage. 
I want to do that so the reader knows what I was learning x hours into the journey, but the goal isn't to teach the reader. Rather, I want to point to the resources that were useful to me.

The seven-part series was very useful.

As for what I will focus on next: I'm going to be taking notes in vim, so the number of hours I will be using vim will go up. I will also gradually cover the chapters in the book by Oualline.

Oh, I forgot something: to set up inverse search and forward search (in short, I can save a `.tex` file in the editor and it gets compiled and updated in the pdf viewer; and I can click on something in the `.tex` document open in the pdf viewer and the cursor in the editor goes to the corresponding location) I had to start using `neovim` rather than `vim`.





