## VIM Setup

### Installing VIM

- brew install vim

### Configuring VIM with dotfiles

- mkdir ~/bin && cd $_
- git clone https://github.com/arcseldon/dotfiles-vim.git 
- mkdir -p dotfiles/vim/bundle
- git clone https://github.com/VundleVim/Vundle.vim.git ~/bin/dotfiles/vim/bundle/Vundle.vim
- cd ~
- ln -nfs ~/bin/dotfiles/vim/vimrc .vimrc
- ln -nfs ~/bin/dotfiles/vim .vim
- vim +PluginInstall +qall   (alternatively launch vim and run :PluginInstall)

###  VIM Tutorial

A [custom VIM Tutorial](https://github.com/arcseldon/dotfiles-vim/blob/master/vim/vimtutor.md) has been prepared that references all the standard VIM keyboard bindings, as well as Plugin bindings and custom bindings that this set of VIM dotfiles is configured for. It should be a great follow-up to the doing the standard VIM `vimtutor` and reading the [Practical Vim](https://pragprog.com/book/dnvim2/practical-vim-second-edition) by Drew Neil.  It is the opinion of this author that both serve a great introductory path to mastering VIM.




