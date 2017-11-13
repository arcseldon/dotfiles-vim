#   V I M   T u t o r i a l  

Vim is a very powerful editor that has many commands.

This is an opinionated tutorial to document & explain 3 main areas:

1. VIM keyboard Shortcuts - reusable VIM bindings & customised improvements

2. Tips and ways to improve the VIM flow (efficient options)

3. VIM Plugins - an opinionated list of essential VIM plugins


The approximate time required to complete the tutor is 60 minutes
(if you are already an expert.. :D )

Tip:  Think of VIM as a finite state machine

All about Modes and Operators

```
:g/re/p  eg. :g/Tutor/p
```

Where grep got its name from..


## History

Splash screen offers some basic information.

```
$ vim -u NONE -N
```

Provides a great foundation for building on top of.
Bare bones, extremely extensible / no plugins.

History - Bill Joy (USA) - co-founded Sun Microsystems in 1982
Joy's renowned CS, said that he wrote the vi editor in a weekend
in 1976... :)

Bram Moolenaar (Dutch) authored VIM (circa 1991).
The Vim editor started as "Vi IMitation" on the Amiga in 1988
Later relabeled "Vi IMproved" and ported to many other platforms

Works at Google.  He is also the maintainer and release manager
of the Vim editor since 1992

vimtutor es -u NONE -N   (to open with spanish language support)

Shout out to Practical VIM by Drew Neil


## Lesson 1.0 Getting Help

Type  :help  or press <F1> or <Help>  to open a help window.

Type  :help cmd  to find help on  cmd .

Create a vimrc startup script to keep your preferred settings.

When typing a  :  command, press CTRL-D to see possible completions.
Press <TAB> to use one completion.


Tip:   :verbose map imap vmap     :verbose map <leader>q

Tip: <c-]> <c-t> <c-o> vert :h unimpaired

Tip: :h lin <tab>  (example only of how to get context)

gf Jump to file name under the cursor

<c-]> <c-t>


## Lesson 1.1: CREATE A STARTUP SCRIPT

** Enable Vim features **

To see standard vim load with     vim -u NONE -N

Vim has many more features than Vi, but most of them are disabled by
default.  To start using more features you have to create a "vimrc" file.

Start editing the "vimrc" file.  This depends on your system:

```
:e ~/.vimrc   for Unix
```

For more information type  :help vimrc-intro

Tip: See git@bitbucket.org:arcseldon/dotfiles-vim.git 

Installing VIM

```
$ brew install vim
```

A quick word on plugins (more on this later):

Vim is extensible via its own language VimScript

There are many plugins that you can take advantage of,
most of which can be found at vim.org


vundle for plugin management
airline for some essential UI features
nerdtree for directory / file management & navigation

More aesthetically pleasing status bar

vim-fugitive - telling which branch in git on
vim-gitgutter - what has been modified / deleted


## Lesson 1.2: THEMES

Wide selection - easy to alter the theme for VIM.

Tip: f8 mapped to cobalt2 and "night" theme

Entry level point for writing your own "vim plugin"


## Lesson 1.3: DIAGNOSING ISSUES

```
:map ,r?
:verbose map <leader>q?
:!echo $VIMRUNTIME
:version
:set runtimepath?
```


## Lesson 1.4: BUFFERS

** To view buffer list, :ls **

```
bn bp bf bl

Unimpaired plugin [b ]b

bufdo bd

ctrl ^    - to go to alternate buffer

Tip: args  args *.exs  args **/*.ex

Use with Airline extensions nav bar

map <leader>-  to automatically clear buffers
```


## Lesson 1.x: WINDOWS

** Windows are views onto buffers **

```
ctrl w s  - split window horizontally

ctrl w v  - split window vertically

:e filename    - to open file from within vim

:sp filename    - to split and open file you want at same time

:only   - to close all windows except the current one

ctrl-w w     - cycles between windows

vsp  spl

<c-w> h j k l

<c-w>x

<c-w> |

<c-w> =

100<c-w>|  open 100 wide

Tip: :vert h

Nerdtree go o   gs s   gi i

<C-w>= Equalize width and height of all windows

<C-w>_ Maximize height of the active window

<C-w>| Maximize width of the active window

[N]<C-w>_ Set active window height to [N] rows

[N]<C-w>| Set active window width to [N] columns

```


## Lesson 1.1:  MOVING THE CURSOR

** To move the cursor, press the h,j,k,l keys as indicated. **

<shift> H M L

zt zz zb

<c-O>zz    drop into insert normal mode to redraw screen in
            centre and carry on typing

() sentence

{} paragraph

<c-f>  <c-b>

<c-d> <c-u>

f{char} t{char}

* #  searching word under cursor

  Tip:  * #  searching word under cursor  modified for any selection

  f{char} Forward to the next occurrence of {char}

  F{char} Backward to the previous occurrence of {char}

  t{char} Forward to the character before the next occurrence of {char}

  T{char} Backward to the character after the previous occurrence of {char}

  ; Repeat the last character-search command

  , Reverse the last character-search command


##  Lesson 1.2: EXITING VIM

Type:  :q! <ENTER>.

This exits the editor, DISCARDING any changes you have made.

NOTE:  :q! <ENTER>  discards any changes you made.

Tip:  wq! wall qall


## Lesson 1.3: TEXT EDITING - DELETION

** Press  x  to delete the character under the cursor. **

Exercise: The ccow jumpedd ovverr thhe mooon

Tip: Spell checking - unimpaired plugin =os [s ]s  z=


## Lesson 1.4: TEXT EDITING - INSERTION

** Press  i  to insert text. **

Exercise: There is text misng this .
Exercise: There is some text missing from this line.


Tip: Normal mode - chunks your undos

Anything that changed doc during normal, visual and command-line modes
i{insert some text}<Esc>  constitutes a change. considered a single change

<c-a> and <c-x> to increment / decrement number

90   90<c-a>

.news { background-position: -180px 0px }


## Lesson 1.5: TEXT EDITING - APPENDING

** Press  A  to append text. **

Exercise: There is some text missing from th

There is some text missing from this line.

Exercise: There is also some text miss

There is also some text missing here.


## Lesson 1.6: EDITING A FILE

** Use  :wq  to save a file and exit. **

!! NOTE: Before executing any of the steps below, read this entire lesson!!

Save the file with changes and exit Vim with:  :wq  <ENTER>

Tip: jj can be used to write and escape at same time


## Lesson 1 SUMMARY

1. The cursor is moved using either the arrow keys or the hjkl keys.
h (left) j (down)       k (up)     l (right)

2. To start Vim from the shell prompt type:  vim FILENAME <ENTER>

3. To exit Vim type:     <ESC>   :q!   <ENTER>  to trash all changes.
OR type:    <ESC>   :wq   <ENTER>  to save the changes.

4. To delete the character at the cursor type:  x

5. To insert or append text type:
i   type inserted text   <ESC>   insert before the cursor
A   type appended text   <ESC>         append after the line

NOTE: Pressing <ESC> will place you in Normal mode or will cancel
an unwanted and partially completed command.


## Lesson 2.1: DELETION COMMANDS

** Type  dw  to delete a word. **

Exercise: There are a some words fun that don't belong paper in this sentence.


## Lesson 2.2: MORE DELETION COMMANDS

** Type  d$  to delete to the end of the line. **

Exercise: Somebody typed the end of this line twice. end of this line twice.

Tip:  D does the same thing


## Lesson 2.3: ON OPERATORS AND MOTIONS

Many commands that change text are made from an operator and a motion.
The format for a delete command with the  d  delete operator is as follows:

d   motion

Where:
d      - is the delete operator.
motion - is what the operator will operate on (listed below).

A short list of motions:
w - until the start of the next word, EXCLUDING its first character.
e - to the end of the current word, INCLUDING the last character.
$ - to the end of the line, INCLUDING the last character.

Thus typing  de  will delete from the cursor to the end of the word.

NOTE:  Pressing just the motion while in Normal mode without an operator will
move the cursor as specified.


## Lesson 2.4: USING A COUNT FOR A MOTION

** Typing a number before a motion repeats it that many times. **

Exercise: This is just a line with words you can move around in.


## Lesson 2.5: USING A COUNT TO DELETE MORE

** Typing a number with an operator repeats it that many times. **

Exercise:  this ABC DE line FGHI JK LMN OP of words is Q RS TUV cleaned up.

Tip: I use the DOT operation . ALL THE TIME !!! like a mini macro


## Lesson 2.6: OPERATING ON LINES

** Type  dd   to delete a whole line. **

Exercise:  1)  Roses are red,
Exercise:  2)  Mud is fun,
Exercise:  3)  Violets are blue,
Exercise:  4)  I have a car,
Exercise:  5)  Clocks tell time,
Exercise:  6)  Sugar is sweet
Exercise:  7)  And so are you.


## Lesson 2.7: THE UNDO COMMAND

** Press  u  to undo the last commands,   U  to fix a whole line. **
type CTRL-R (keeping CTRL key pressed while hitting R) a few times
to redo the commands (undo the undo's).

Exercise: Fiix the errors oon thhis line and reeplace them witth undo.


## Lesson 2 SUMMARY

1. To delete from the cursor up to the next word type:    dw
2. To delete from the cursor to the end of a line type:    d$
3. To delete a whole line type:    dd

4. To repeat a motion prepend it with a number:   2w
5. The format for a change command is:
operator   [number]   motion
where:
operator - is what to do, such as  d  for delete
[number] - is an optional count to repeat the motion
motion   - moves over the text to operate on, such as  w (word),
$ (to the end of line), etc.

6. To move to the start of the line use a zero:  0

7. To undo previous actions, type:         u  (lowercase u)
To undo all the changes on a line, type:  U  (capital U)
To undo the undo's, type:           CTRL-R


## Lesson 3.1: THE PUT COMMAND

** Type  p  to put previously deleted text after the cursor. **

Exercise: d) Can you learn too?
Exercise: b) Violets are blue,
Exercise: c) Intelligence is learned,
Exercise: a) Roses are red,

Tip:  It is possible to use "bubbling" too .. z Up and z Down. (visual too)
(rarely use this..)


## Lesson 3.2: THE REPLACE COMMAND

** Type  rx  to replace the character at the cursor with  x . **

Exercise:  Whan this lime was tuoed in, someone presswd some wrojg keys!
Exercise:  When this line was typed in, someone pressed some wrong keys!


## Lesson 3.3: THE CHANGE OPERATOR

** To change until the end of a word, type  ce . **

Exercise: This lubw has a few wptfd that mrrf changing usf the change operator.
Exercise: This line has a few words that need changing using the change operator.

Notice that  ce  deletes the word and places you in Insert mode.


## Lesson 3.4: MORE CHANGES USING c

** The change operator is used with the same motions as delete. **

1. The change operator works in the same way as delete.  The format is:

c    [number]   motion

2. The motions are the same, such as   w (word) and  $ (end of line).
3. Move to the first line below marked Exercise:.
4. Move the cursor to the first error.
5. Type  c$  and type the rest of the line like the second and press <ESC>.

Exercise: The end of this line needs some help to make it like the second.
Exercise: The end of this line needs to be corrected using the  c$  command.

NOTE:  You can use the Backspace key to correct mistakes while typing.


Tip: In insert mode:
<c-w> delete back one word
<c-u> delete back to start of line

Indent block <shift> >  and dedent  <shift> <


## Lesson 3 SUMMARY

1. To put back text that has just been deleted, type   p .  This puts the
deleted text AFTER the cursor (if a line was deleted it will go on the
line below the cursor).

2. To replace the character under the cursor, type   r   and then the
character you want to have there.

3. The change operator allows you to change from the cursor to where the
motion takes you.  eg. Type  ce  to change from the cursor to the end of
the word,  c$  to change to the end of a line.

4. The format for change is:

c   [number]   motion

Now go on to the next lesson.


## Lesson 4.1: CURSOR LOCATION AND FILE STATUS

** Type CTRL-G to show your location in the file and the file status.
Type  G  to move to a line in the file. **

2. Press  G  to move you to the bottom of the file.
Type  gg  to move you to the start of the file.

3. Type the number of the line you were on and then  G .  This will
return you to the line you were on when you first pressed CTRL-G.


Tip: marks ma mb `a `b etc    <c-o> <c-i>   search /  ?


## Lesson 4.2: THE SEARCH COMMAND

** Type  /  followed by a phrase to search for the phrase. **

1. In Normal mode type the  /  character.  Notice that it and the cursor
appear at the bottom of the screen as with the  :  command.

2. Now type 'errroor' <ENTER>.  This is the word you want to search for.

3. To search for the same phrase again, simply type  n .
To search for the same phrase in the opposite direction, type  N .

4. To search for a phrase in the backward direction, use  ?  instead of  / .

5. To go back to where you came from press  CTRL-O  (Keep Ctrl down while
pressing the letter o).  Repeat to go back further.  CTRL-I goes forward.

Exercise:  "errroor" is not the way to spell error;  errroor is an error.

NOTE: When the search reaches the end of the file it will continue at the
start, unless the 'wrapscan' option has been reset.

Tip:  search word under cursor * # , search visual selection

Would like a bacon sandwich
Would like a bacon sandwich
Would like a bacon sandwich

Would like a bacon sandwich
Would like a bacon sandwich
Would like a bacon sandwich

can use a mark to specify range of search / replace

.,'as/bacon/lettuce

use o to jump to top and bottom of visual region

:g/bacon/p

:g/re/p

:%!sort -u

:g/^$/d


:g/bacon/normal O@doc


You could emulate grep -v by deleting lines that match foo:

:g/foo/normal dd

Or you could append all lines matching foo to register a:

:g/foo/normal "Ay


## Lesson 4.3: MATCHING PARENTHESES SEARCH

** Type  %  to find a matching ),], or } . **

Exercise: This ( is a test line with ('s, ['s ] and {'s } in it. ))

NOTE: This is very useful in debugging a program with unmatched parentheses!


## Lesson 4.4: THE SUBSTITUTE COMMAND

** Type  :s/old/new/g  to substitute 'new' for 'old'. **

Type  :s/thee/the <ENTER> .  Note that this command only changes the
first occurrence of "thee" in the line.

Now type  :s/thee/the/g .  Adding the  g  flag means to substitute
globally in the line, change all occurrences of "thee" in the line.

Exercise: thee best time to see thee flowers is in thee spring.

4. To change every occurrence of a character string between two lines,
type   :#,#s/old/new/g    where #,# are the line numbers of the range
of lines where the substitution is to be done.
Type   :%s/old/new/g      to change every occurrence in the whole file.
Type   :%s/old/new/gc     to find every occurrence in the whole file,
with a prompt whether to substitute or not.


## Lesson 4 SUMMARY

1. CTRL-G  displays your location in the file and the file status.
G  moves to the end of the file.
number  G  moves to that line number.
gg  moves to the first line.

2. Typing  /  followed by a phrase searches FORWARD for the phrase.
Typing  ?  followed by a phrase searches BACKWARD for the phrase.
After a search type  n  to find the next occurrence in the same direction
or  N  to search in the opposite direction.
CTRL-O takes you back to older positions, CTRL-I to newer positions.

3. Typing  %  while the cursor is on a (,),[,],{, or } goes to its match.

4. To substitute new for the first old in a line type    :s/old/new
To substitute new for all 'old's on a line type     :s/old/new/g
To substitute phrases between two line #'s type     :#,#s/old/new/g
To substitute all occurrences in the file type    :%s/old/new/g
To ask for confirmation each time add 'c'       :%s/old/new/gc


## Lesson 5.1: HOW TO EXECUTE AN EXTERNAL COMMAND

** Type  :!  followed by an external command to execute that command. **

Example :!ls

Tip:    :%!sort -u


## Lesson 5.2: MORE ON WRITING FILES

** To save the changes made to the text, type  :w FILENAME. **

Type :!ls  to get a listing of your directory.
You already know you must hit <ENTER> after this.

Choose a filename that does not exist yet, such as TEST.

Now type:   :w TEST   (where TEST is the filename you chose.)

NOTE: If you were to exit Vim and start it again with  vim TEST , the file
would be an exact copy of the tutor when you saved it.

Now remove the file by typing (Unix): :!rm TEST


## Lesson 5.3: SELECTING TEXT TO WRITE

** To save part of the file, type  v  motion  :w FILENAME **

Press  v  and move the cursor to the fifth item below.  Notice that the
text is highlighted.

```
Press the  :  character.  At the bottom of the screen  :'<,'> will appear.
```

Type  w TEST  , where TEST is a filename that does not exist yet.  Verify

```
that you see  :'<,'>w TEST  before you press <ENTER>.
```

5. Vim will write the selected lines to the file TEST.

NOTE:  Pressing  v  starts Visual selection.


Tip: gv  re-highlight last selected visual block


## Lesson 5.4: RETRIEVING AND MERGING FILES

** To insert the contents of a file, type  :r FILENAME  **

:r TEST   where TEST is the name of the file you used.

The file you retrieve is placed below the cursor line.


## Lesson 5 SUMMARY

1.  :!command  executes an external command.

2.  :w FILENAME  writes the current Vim file to disk with name FILENAME.

3.  v  motion  :w FILENAME  saves the Visually selected lines in file
FILENAME.

4.  :r FILENAME  retrieves disk file FILENAME and puts it below the
cursor position.

5.  :r !ls  reads the output of the ls command and puts it below the
cursor position.


## Lesson 6.1: THE OPEN COMMAND

** Type  o  to open a line below the cursor and place you in Insert mode. **
To open up a line ABOVE the cursor, simply type a capital O , rather
than a lowercase  o.  Try this on the line below.

Exercise: Open up a line above this by typing O while the cursor is on this line.


## Lesson 6.2: THE APPEND COMMAND

** Type  a  to insert text AFTER the cursor. **

Exercise: This li will allow you to pract appendi text to a line.
Exercise: This line will allow you to practice appending text to a line.


## Lesson 6.3: ANOTHER WAY TO REPLACE

** Type a capital  R  to replace more than one character. **

Exercise: Adding 123 to xxx gives you xxx.
Exercise: Adding 123 to 456 gives you 579.

NOTE:  Replace mode is like Insert mode, but every typed character deletes an
existing character.


## Lesson 6.4: COPY AND PASTE TEXT

** Use the  y  operator to copy text and  p  to paste it **

Use Visual mode to select " item.", yank it with  y , move to the end of
the next line with  j$  and put the text there with  p .

Exercise:  a) this is the first item.
b)

NOTE: you can also use  y  as an operator;  yw  yanks one word.


Tip:  gv - to reselect a highlighed region


## Lesson 6.5: SET OPTION

** Set an option so a search or substitute ignores case **

1. Search for 'ignore' by entering:   /ignore  <ENTER>
Repeat several times by pressing  n .

2. Set the 'ic' (Ignore case) option by entering:   :set ic

4. Set the 'hlsearch' and 'incsearch' options:  :set hls is

5. Now type the search command again and see what happens:  /ignore <ENTER>

6. To disable ignoring case enter:  :set noic

NOTE:  To remove the highlighting of matches enter:   :nohlsearch
NOTE:  If you want to ignore case for just one search command, use  \c
in the phrase:  /ignore\c  <ENTER>


Tip:  Use vim-unimpaired plugin for most of your needs


## Lesson 6 SUMMARY

1. Type  o  to open a line BELOW the cursor and start Insert mode.
Type  O  to open a line ABOVE the cursor.

2. Type  a  to insert text AFTER the cursor.
Type  A  to insert text after the end of the line.

3. The  e  command moves to the end of a word.

4. The  y  operator yanks (copies) text,  p  puts (pastes) it.

5. Typing a capital  R  enters Replace mode until  <ESC>  is pressed.

6. Typing ":set xxx" sets the option "xxx".  Some options are:
'ic' 'ignorecase' ignore upper/lower case when searching
'is' 'incsearch'  show partial matches for a search phrase
'hls' 'hlsearch'  highlight all matching phrases
You can either use the long or the short option name.

7. Prepend "no" to switch an option off:   :set noic


## Lesson 7.3: COMPLETION

** Command line completion with CTRL-D and <TAB> **

1. Make sure Vim is not in compatible mode:  :set nocp

2. Look what files exist in the directory:  :!ls   or  :!dir

3. Type the start of a command:  :e

4. Press  CTRL-D  and Vim will show a list of commands that start with "e".

5. Press <TAB>  and Vim will complete the command name to ":edit".

6. Now add a space and the start of an existing file name:  :edit FIL

7. Press <TAB>.  Vim will complete the name (if it is unique).

NOTE:  Completion works for many commands.  Just try pressing CTRL-D and
<TAB>.  It is especially useful for  :help .


## Lesson 8.1: FOLDS

** How to use Folds  **

set foldmethod=syntax
set foldlevelstart=20

zf zd

zc zo za   zR zM

Tip: Use folds for navigation, deletion, can be used with marks

set foldmethod=syntax

zj go to next fold
zo  open fold
zc close fold
za  toggle fold
zk  back up to start of previous fold

zM close all
zR  open all
zx folds everything except one at cursor line

set foldmethod=indent

zf#j creates a fold from the cursor down # lines.
zf/string creates a fold from the cursor to string.
zj moves the cursor to the next fold.
zk moves the cursor to the previous fold.
zo opens a fold at the cursor.
zO opens all folds at the cursor.
zm increases the foldlevel by one.
zM closes all open folds.
zr decreases the foldlevel by one.
zR decreases the foldlevel to zero -- all folds will be open.
zd deletes the fold at the cursor.
zE deletes all folds.
[z move to start of open fold.
]z move to end of open fold.


Tip:

Folds are useful for deletion, navigation, page real-estate, 
and performing search and replace :s/a/b/g 


## Lesson 8.2: Marks

m{a-z}   -  set a mark
`{a-z}  - go to mark
'{a-z}   - go to beginning of line of mark

`` Position before the last jump within current file
`. Location of last change
`^ Location of last insertion
`[ Start of last change or yank
`] End of last change or yank
`< Start of last visual selection
`> End of last visual selection


## Lesson 8.2: MACROS

** How to use macros  **

In normal mode, qa  perform actions  then in normal mode q

Tip: very useful for organising lists etc


## Lesson 8.3: Multi-Cursors

** How to use multi-cursors  **

Save changes to many files at once
Rename a variable in many places at once

<leader>m  <c-n> <c-p> <c-x>

Exercise:

defmodule Hello do
def to(badparam) do
IO.puts 'Hello #{badparam}'
IO.inspect badparam'
end
end


Mon
Tue
Wed
Thu
Fri
Sat
Sun

Similar to Sublime Text's behaviour. vim-multiple-cursors plugin


Tip:


## Lesson 8.4: Surround Tags

** How to use vim-unimpaired **

Surround things with {}, (), [], "", '', <xml></xml>

Hello "World"

```
"VS<h1>

veS”

veS<em>

to change existing tag cst  (change surrounding tag)

cst<h1>

dst   (delete surrounding tag)

to surround in single quotes

vimS’

to change from single quote to double quote

cs’”

to delete the double quotes

ds”

```



## Lesson 8.4: Auto-Completion

** How to do tab completion of code **

Vim has a built-in completion feature that you can trigger by
just using <C-X> (that's the control-x key)

and then another control-key sequence like <C-F> to complete filenames
or <C-O> to trigger omni-completion.

<ctrl>n for generic completion
<ctrl>n to then traverse list down
<ctrl>p to travese list upwards


Tip: supertab plugin not compatible with snipmate

youcompleteme is complex - can integrate with eclim (headless eclipse)


## Lesson 8.4: CTAG Support

** How to use CTAGS**

Parses code files and generates a meaningful "tag" file which is used
by vim to "jump to definition"

Don't use the default shipped with mac. Insteall install
with `brew install ctags` and ensure

use `ctags` command to update the "tags" file

:tag <name of tag to look for>

:ts

Tip: <leader>ct to generate ctag file


## Lesson 8.4: GIT Support

** How to use GIT in VIM**

Vim Fugitive

Perform git operations in git: Blame, log, write/stage, commit

Git-Gutter

Show line changes in line gutter

Revert, commit, preview hunk changes

:Gstatus
:Gdiff
:gl

Tip: Mostly use the command line

## Easymotion

,,w  for a quick demonstration


## Lesson 8.5: CtrlP - Search Files

** How to search files efficiently **

use CtrlP plugin

uses fuzzy logic

## Ctrl-P

Quick file lookup, and more..

<f5> to purge the cache (see new files etc)

ctrl-k
ctrl-j   to nav. the results

<c-b> to switch between various search range options

Press <F5> to purge the cache for the current directory to get new files

Use <c-z> to mark/unmark multiple files and <c-o> to open them.

Use <c-t> or <c-v>, <c-x> to open the selected entry in a new tab
or in a new split.

<c-d> to turn to file only search mode

<c-y> if you enter full path and file doesn’t exist will create it

Use <c-z> to mark/unmark multiple files and <c-o> to open them.

'kaneshin/ctrlp-git-log'

" open ctrlp-git-log (git log)
map <leader>gl :CtrlPGitLog<CR>


Tip: <leader>f


## Lesson 8.6: Grep for text in files (cross project)

** How to use Ack **

## Ack  plugin  - (install Ack with brew install ack)

Cli tool like grep but built for programmers
respects file types


Tip: use ctrl-k and ctrl-j to get into and out of quickfix list quickly

map <Leader>A :AckG
map <Leader>a :Ack

Search word under cursor:

map <leader>q  searches word across entire project
map <F4> ack with file type context (only searches with type)


## Lesson 8.6: Search And Replace

** How to use **

Several different ways to do this

Search and replace
1. :Ack <search term>
2. :cdo %s/<search term>/<replace term>/gc
3. (If you want to save the changes in all files) :cdo update


## Lesson 8.4: Copy And Paste Registers

** How to use **

copy and paste from registers

"a yy
"ap

"by2w
"bP

:reg

:reg a

"+y  to yank to system clipboard
"+p to paste from system clipboard


Tip:  Use map <c-c> to copy into unnamed register (system cb), <c-v> works


## Lesson 8.x: Quickfix window

** How to use quickfix window **

:copen " Open the quickfix window
:ccl   " Close it
:cw    " Open it if there are "errors", close it otherwise
:cn    " Go to the next error in the window
:cnf   " Go to the first error in the next file

Tip: unimpaired plugin

[q     cprevious
]q     cnext
[Q     cfirst
]Q     clast


## Lesson 8.x: Jumps  Window

** How to use jumps window **

ctrl-o and ctrl-i to jump backwards and forwards through jump list

:jumps

Tip: unimpaired plugin


## Lesson 8.x: Locations Window

:lop :lopen  :lclose :lcl  :lnext :lprevious

unimpaired

[l  lprevious
]l  lnext
[L  lfirst
]L  llast

Tip: This is used by Syntastic for :Errors !!!


## Lesson 8.x: Changes Window

** How to use changes window **

g;   takes back to where cursor was last used to edit, Keep pressing
g; to go backwards through change list

g,   goes forwards through change list


:changes

Tip: unimpaired plugin


## Miscellaneous

To open URL e.g http://www.google.com - put cursor over url and use `gx`

To format a document (eg. markdown) to wrap at 80 chars use:

```
:set textwidth=80
gq
```


## Conclusion

This concludes the Vim Tutor.  It was intended to give a brief overview of
the Vim editor, just enough to allow you to use the editor fairly easily.
It is far from complete as Vim has many many more commands.  Read the user
manual next: ":help user-manual".

See http://iccf-holland.org/click5.html

## See also

https://github.com/carlhuda/janus

