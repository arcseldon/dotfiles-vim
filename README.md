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






