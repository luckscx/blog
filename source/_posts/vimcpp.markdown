# 目标
在新的开发机上做cpp的vim开发环境

# 基本环境
tlinux 2.2 腾讯内部标准版 基于centos 7 开发，使用yum安装一些基本的库

# 坎坷经历

首先原来是用YCM做的，感觉整个比较重，开始尝试新的NeoVim+Coc+Clangd的方案


## 安装Neovim 
非常简单 官网下载二进制
```
curl -Lo https://github.com/neovim/neovim/releases/download/v0.4.3/nvim.appimage -O ~/bin/nvim
chmod u+x ~/bin/nvim
```

## 安装CoC插件
vimrc配置 这里使用了VimPlug插件
```
call plug#begin('~/.vim/plugged')
Plug 'neoclide/coc.nvim', {'do': { -> coc#util#install() }}
call plug#end()
let g:coc_global_extensions = ['coc-json','coc-python','coc-clangd','coc-snippets']
```

在Vim内执行命令
```
PlugInstall
Coc
```

## 安装Clangd
clangd 是包含在LLVM的clang-tool-extra包内的一个工具，系统自带的版本太低，基本没法用。
尝试下载二进制包安装，但是没有官网没有直接提供Centos版本的，试了两个也不行，只能源码编译。 最新版本是10.0

```
wget https://github.com/llvm/llvm-project/releases/download/llvmorg-10.0.0/llvm-project-10.0.0.tar.xz
tar -xf llvm-project-10.0.0.tar.xz
cd llvm
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release -DLLVM_ENABLE_PROJECTS="clang;clang-tools-extra" -G "Unix Makefiles" ../llvm
make -j24
make install
```
默认是编Debug，试了一下运行Clang CPU满载，有点吓人，换了Release版本效果好很多

## 周边插件整合
为了使用snippets，安装了coc-snippets vimrc添加配置
```
inoremap <silent><expr> <cr> pumvisible() ? coc#_select_confirm() : 
                                           \"\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>""
inoremap <silent><expr> <tab>
      \ pumvisible() ? "\<C-n>" :
      \ <SID>check_back_space() ? "\<tab>" :
      \ coc#refresh()
function! s:check_back_space() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction
```
其中pubvisible函数是VIM内置的，判断当前是否有下拉框打开
用tab触发 和 切换列表下一个
用enter回车确定展开snippet，使用起来最舒服

