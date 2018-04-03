## TMUX Tutorial 

### Resources

- https://github.com/tmux/tmux
- https://pragprog.com/book/bhtmux/tmux
- https://thoughtbot.com/upcase/videos/tmux-introduction

Other conversations:

- https://news.ycombinator.com/item?id=11283955

### Background

- Open source, available on github
- Terminal Multiplexer (TMUX predecessor was GNU Screen)
- Multiple virtual terminal sessions
- wraps around existing shell process
- allows communcication between panes
- The tiling/multiplexing part is one aspect. 
- Another is the fact that it spawns a session that can run persistently in the background and which you can connect to from anywhere. 
- You can also disconnect, let it sit there for a week, come back and it'll still be there exactly as you left it.

### Hipster IDE setup using OS X + tmux + vim + iterm2

- I use tmux as my primary "IDE", 
- Often quoted “indispensable being able to connect to my tmux session from any computer anywhere” - that doesn’t apply to me ... yet..
- Here to offer the best tips, configuration and workflows I have acquired in the relatively short time I have been using TMUX
- Show you some of its capabilities and if you decide you like it, feel free to borrow my dotfiles as starting point / explain best resources for learning more..
- All done with single TMUX client - at no time opening new tabs, or new terminal windows etc

### Why should I care?

- Extremely powerful
- Can handle long running processes - connect to server, kick off a job and disconnect
- Primary usecase (myself) is for local application development to accompany VIM usage
- Spend vast majority of day in terminal and 100% of that time in TMUX
- Workflow / time efficiency - productive mouse-free development

### How To Get Help

- man tmux
- tmux list-commands
- tmux list-commands | grep pane

- Gist cheatsheets
    - https://gist.github.com/arcseldon/3ff52dbee9bd7a5aace342bbc08efa3f

### Installation

- Use package manager
- brew install tmux
- brew info tmux


#### Attach / Detach

- Attach manually
- Detach manually

- Attach automated
- Detach automated

#### Ancillary Scripts

- tat
- .zshrc updates

#### General Execution

- Can use the tmux executable and the tmux command prompt
- Heavily customization available 

#### Creation

- Create Sessions
- Create Windows
- Create Panes

#### Navigation

- Switch between panes
- Switch between windows
    prefix number
- Switch between sessions
    - c-j, c-h, s

- Command mode (:  similar to VIM)
- Alternate between last window
- Alternate between last session

- Resize panes
- Zoom panes
- Swap panes
- Break pane into window
- Bring pane back into current window

#### Rename

- Rename session
- Rename window
- Rename pane

#### Cleanup

- Kill a pane
- Kill a window
- Kill a session

#### Pane Synchronization

- Synchronise panes when running commands

#### Defaults 

- C-a         Send the prefix key (C-b) through to the application.
- $           Rename the current session.
- &           Kill the current window.
- '           Prompt for a window index to select.
- (           Switch the attached client to the previous session.
- )           Switch the attached client to the next session.
- ,           Rename the current window.
- -           Delete the most recently copied buffer of text.
- .           Prompt for an index to move the current window.
- 0 to 9      Select windows 0 to 9.
- :           Enter the tmux command prompt.
- ;           Move to the previously active pane.
- =           Choose which buffer to paste interactively from a list.
- ?           List all key bindings.
- D           Choose a client to detach.
- L           Switch the attached client back to the last session.
- [           Enter copy mode to copy text or view the history.
- ]           Paste the most recently copied buffer of text.
- c           Create a new window.
- d           Detach the current client.
- f           Prompt to search for text in open windows.
- i           Display some information about the current window.
- l           Move to the previously selected window.
- n           Change to the next window.
- o           Select the next pane in the current window.
- p           Change to the previous window.
- q           Briefly display pane indexes.
- r           Force redraw of the attached client.
- m           Mark the current pane (see select-pane -m).
- M           Clear the marked pane.
- s           Select a new session for the attached client interactively.
- t           Show the time.
- w           Choose the current window interactively.

#### VIM Integration

- Compare VIM and TMUX Navigation (plugin support)
- Resize panes with VIM open
- Send commands from VIM to TMUX
- DEMO: Vim, split right IEX, split bottom man page for tmux

leader vf and c-\

##### Demo Notes

- In vim 2 vert splits and right side horizontal split
- Then a right vertical tmux split
- And a lower horizontal tmux split
- Then resize the tmux vertical and horizontal splits
- Then illustrate the zooms too.

- Illustrate copying from VIM to tmux
- leader vo
- then open iex
- data = Enum.to_list(1..10)
- result = Enum.map(data, fn x -> :math.pow(x, 2) end)
- leader vl
- show how to visually select first
- now attach to different pane
- prefix va
- then
- echo "Hello, world"
- and leader vl


use ,va to select runner
use ,vf to focus runner onto runner pane (expanding it to take full screen size)
use ctrl-a ;   to zoom back out and flip back to the original pane before the focus runner command

#### Arbitrary Application Execution

- Run arbitrary apps - eg. htop, irb, iex
- Ctrl-D to exit
- Ctrl C Ctrl C

#### Scrolling, Copy & Paste

- Use tree for the demo to show how to copy / search with ? etc

- prefix [   enters copy mode
- go to start of copy area and use 'v'
- optionally can use 'V' before 'v' to put into rectangle selection mode
- move to end of copy area
- use 'y' to yank
- then 'q' to exit
- or can use escape
- then prefix ]  to paste into vim etc

### Conclusion

Awesome setup with full IDE like power using iterm2, vim, and tmux interoperably.
Final note on my latest workflow. This works great for me in most languages, but
where I really need the power of a decent debugger - I also open JetBrains IDE for
debugging capabilities only (eg. IntelliJ / Webstorm). Could use open source alternative
such as Visual Studio Code for JS. But I do all my editing in any language inside VIM / TMUX.
