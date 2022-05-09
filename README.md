# My C++ and C language project boilerplate in Windows
Master branch is targeting c++ project.
## editor setup
My editor is using neovim Windows with clangd lsp server. My step preparing my editor is:
- Install [scoop installer](https://scoop.sh/).
- Install Mingw compiler by command `scoop install mingw`.
- Install neovim by command `scoop install neovim` or `scoop install neovim-nightly`.
- Install clangd using [nvim-lsp-installer](https://github.com/williamboman/nvim-lsp-installer).
- Setup clangd using [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) plugin.

## clangd setup
My config mainly using compile_flags.txt for clangd. the flag is:
- `-lstdc++`, this flag is used to notify clang that this c++ project and include c++ header. If this flag is removed in c++ project or file .cpp, clang only using c header. example:remove this flag, clangd error cant find include<iostream>. Remove this flag if using c based project.
- `-target x86_64-pc-windows-gnu`, this flag is used to notify clang that this project is using mingw 64bit windows. Removing this flag, clang can't find your include header.
