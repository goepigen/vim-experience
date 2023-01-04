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

Here are commands which I am using but only because I saw them on the internet (I don't fully understand why these commands are what they are and haven't had time to investigate yet)
- `diw`: delete entire word the cursor is on 

Here are things I notice I haven't memorized very well yet
- I confuse `j` and `k` a lot: it seems that my natural instinct is to think that `j` means up and `k` means down, but it is the opposite.
- The `ESC` key seems to far away given how important and frequent it is to go to NORMAL mode

Here are some other interesting links I've read at this point in the journey

- [Differences between Emacs and Vim](https://stackoverflow.com/questions/1430164/differences-between-emacs-and-vim)
- [Gilles Castel: How I'm able to take notes in mathematics lectures using Latex and Vim](https://castel.dev/post/lecture-notes-1/)

This particular article is what actually made me decide to commit to learning vim. 
I was about to take notes from a Chemistry course in Google Docs. Then I thought: Latex would be better. 

So I fired up TexShop. 

Then I noticed that it wasn't a particularly efficient process writing there. So I googled something like "best vim editor for mac" and quickly stumbled on people talking about vim plugins that enable you to use latex. 

Next, I found [this youtube video](https://www.youtube.com/watch?v=DOtM1mrWjUo) of a guy called Charlie Mars who has an awesome setup for making Latex documents using vim while listening to a lecture. He said he was heavily inspired by the article by Gilles Castel, and that is how I stumbled upon that article.
