# vim-setup for go dev

## Step 1
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
git clone https://github.com/fatih/vim-go.git ~/.vim/plugged/vim-go
```

## Step 2
Create `~/.vimrc` with following content:

```
call plug#begin()
Plug 'fatih/vim-go', { 'do': ':GoInstallBinaries' }
call plug#end()
```
## Step 3
Open vim, execute `:GoInstallBinaries`
Let it run and install stuff

