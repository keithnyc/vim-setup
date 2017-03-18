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
Plug 'fatih/molokai'
call plug#end()

let g:rehash256 = 1
let g:molokai_original = 1
colorscheme molokai

" write file whenever you try to GoBuild
set autowrite

"allow copy/paste from sys clipboard
set clipboard=unnamed

" run :GoBuild or :GoTestCompile based on the go file
function! s:build_go_files()
  let l:file = expand('%')
  if l:file =~# '^\f\+_test\.go$'
    call go#cmd#Test(0, 1)
  elseif l:file =~# '^\f\+\.go$'
    call go#cmd#Build(0)
  endif
endfunction

~                             


```
## Step 3
Open vim, execute `:GoInstallBinaries`
Let it run and install stuff

Reopen vim and execute `:PlugInstall` for the color scheme plugin

