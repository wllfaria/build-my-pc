# Build my pc

Repository built to bootstrap your new pc configuration for development

## Contents
* [Installing softwares](#installing-softwares)
	* [Softwares on Windows](#softwares-on-windows)
* [Visual Studio Code Setup](#visual-studio-code-setup)
* [Neovim Setup](#neovim-setup)
* [Git Configuration](#git-configuration)

## Installing Softwares

Software installation guides based on OS

### Softwares on Windows

<p align="center"><em><small><a href="#contents">Missclicked? Go back!</a></small></em></p>

On Windows, I utilize chocolatey as a package manager, so the first step is to install it.

* [Chocolatey](https://chocolatey.org/install)

Once you've installed chocolatey, you can now start installing other softwares below:

####  Visual Studio Code
```shell
choco install vscode
```

> After installing VSCode, refer to the [VSCode configuration guide.](#visual-studio-code-setup)


#### Opera
```shell
choco install opera-gx
```

#### NVM

<small><em>I utilize NVM for managing NodeJS versions</em></small>
```shell
choco install nvm
```

#### Yarn

```shell
choco install yarn
```

#### Neovim

<small><em>Neovim is my main editor even though I still use VSCode sometimes.</em></small>

```shell
choco install neovim
```

> After installing Neovim, refer to the [Neovim configuration guide.](#neovim-setup)

#### Git

```shell
choco install git
```

> After installing Git, refer to the [Git configuration guide.](#git-configuration)

#### MinGW

```shell
choco install mingw
```

### Visual Studio Code Setup

<p align="center"><em><small><a href="#contents">Missclicked? Go back!</a></small></em></p>

The first step is to install all the extensions, I've sorted in two sections, aesthetics and functional.

#### Functional Extensions

Extensions that add functionalities to VSCode, such as vim emulation

```bash
code --install-extension alexcvzz.vscode-sqlite
code --install-extension christian-kohler.path-intellisense
code --install-extension christian-kohler.npm-intellisense
code --install-extension zignd.html-css-class-completion
code --install-extension shamanu4.django-intellisense
code --install-extension esbenp.prettier-vscode
code --install-extension dbaeumer.vscode-eslint
code --install-extension eamodio.gitlens
code --install-extension kamikillerto.vscode-colorize
code --install-extension msjsdiag.debugger-for-chrome
code --install-extension editorconfig.editorconfig
code --install-extension ms-python.python
code --install-extension ms-dotnettools.csharp
code --install-extension vscjava.vscode-java-pack
code --install-extension coenraads.bracket-pair-colorizer-2
code --install-extension oderwat.indent-rainbow
code --install-extension wix.vscode-import-cost
code --install-extension dkundel.vscode-new-file
code --install-extension ritwickdey.liveserver
code --install-extension rvest.vs-code-prettier-eslint
code --install-extension vscodevim.vim
code --install-extension jpoissonnier.vscode-styled-components
```

#### Aesthetics Extensions

Extensions that make VSCode prettier, such as themes and others

```bash
code --install-extension pkief.material-icon-theme
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension shd101wyy.markdown-preview-enhanced
code --install-extension teabyii.ayu
code --install-extension adpyke.codesnap
```

#### Settings JSON

```json
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript", "typescript", "typescriptreact", "javascriptreact"],
    "editor.fontFamily": "FiraCode Nerd Font",
    "vim.insertModeKeyBindings": [
        {
            "before": ["j", "k"],
            "after": ["<Esc>"]
        },
        {
            "before": ["k", "j"],
            "after": ["<Esc>"]
        }
    ],
    "editor.fontLigatures": true,
    "editor.cursorStyle": "line",
    "editor.suggestSelection": "first",
    "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
    "workbench.iconTheme": "material-icon-theme",
    "window.zoomLevel": 1,
    "explorer.confirmDragAndDrop": false,
    "explorer.confirmDelete": false
}
```

### Neovim Setup

<p align="center"><em><small><a href="#contents">Missclicked? Go back!</a></small></em></p>

Quick start configuration for Neovim. The following files must be created in the Neovim default configuration folder.

#### Linux and MacOS

The default configuration folder for Linux and MacOS is located at `~/.config/nvim`. If this folder doesn't exist, you can create it yourself.

#### Windows

The default configuration folder for Windows is located at `C:\Users\{username}\AppData\Local\nvim`. If this folder doesn't exist, you can create it yourself.

#### Configuration

The first step is to install a plugin manager. This makes easier to install and uninstall vim plugins. I use vim-plug, so let's install it

* [Vim-Plug](https://github.com/junegunn/vim-plug)

After the installation, restart your vim and on the configuration folder, you'll create some files with the contents listed below.

##### plugins.vim
```vim
call plug#begin(stdpath('data'))
" NERDTree Plugins
Plug 'preservim/nerdtree'								" File Tree viewer plugin
Plug 'Xuyuanp/nerdtree-git-plugin'							" Git integration for NERDTree
Plug 'tiagofumo/vim-nerdtree-syntax-highlight'						" Syntax Highlight for NERDTree
Plug 'ryanoasis/vim-devicons'								" File icons for NERDTree			

" Git Integration Plugins
Plug 'airblade/vim-gitgutter'								" Integrate signs on the side of modified files

" DevExp Plugins
Plug 'neoclide/coc.nvim', {'branch': 'release'}						" Intellisense and autocompletion
Plug 'christoomey/vim-tmux-navigator'							" Split navigation like Tmux
Plug 'preservim/nerdcommenter'								" Comment toggler for neovim
Plug 'HerringtonDarkholme/yats.vim'							" Typescript syntax highlight
Plug 'octol/vim-cpp-enhanced-highlight'							" C++ syntax highlight
Plug 'numirias/semshi'									" Python syntax highlight
Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }					" Fuzzy Finder core
Plug 'junegunn/fzf.vim'									" Fuzzy Finder neovim extension
Plug 'mhinz/vim-startify'								" Fancy Start Screen
Plug 'chrisbra/Colorizer'								" Color hex and rgb highlight
Plug 'editorconfig/editorconfig-vim'                                                    " Editorconfig for neovim                
Plug 'styled-components/vim-styled-components'                                          " Styled components syntax highlight
Plug 'alvan/vim-closetag'								" Auto close html tags

" Theming Plugins
Plug 'vim-airline/vim-airline'								" Airline status bar
Plug 'vim-airline/vim-airline-themes'							" Neovim airline themes
Plug 'ayu-theme/ayu-vim'								" Ayu theme for neovim
call plug#end()

" Some basic configuration needed for some plugins

" Theming configuration
set termguicolors									" Enabling teminal colors
let ayucolor="light"									" Setting ayu to use light theme
colorscheme ayu										" Setting neovim to use Ayu as its theme

" COC configuration, this adds global extensions to COC
let g:coc_global_extensions = [
  \ 'coc-snippets',
  \ 'coc-pairs',
  \ 'coc-tsserver',
  \ 'coc-eslint',
  \ 'coc-prettier',
  \ 'coc-json',
  \ ]

" NERDCommenter configuration
let g:NERDSpaceDelims = 1								" Adds 1 space between comment and code
let g:NERDCompactSexyComs = 1								" Use compact syntax for comments

" C++ syntax highlight configuration
let g:cpp_class_scope_highlight = 1							" Enable highlighting of class scopes
let g:cpp_member_variable_highlight = 1							" Enable highlighting of member variables

" NERDTree configuration
let g:NERDTreeGitStatusWithFlags = 1							" Enable git status with flags
let g:NERDTreeIgnore = ['^node_modules$']						" Ignore node_modules folder
```

##### keymaps.vim

```vim
" COC keybindings
nmap <silent> [g <Plug>(coc-diagnostic-prev)						" Go to previous diagnostic
nmap <silent> ]g <Plug>(coc-diagnostic-next)						" Go to next diagnostic
nmap <silent> gd <Plug>(coc-definition)							" Go to definition
nmap <silent> gy <Plug>(coc-type-definition)						" Go to type definition
nmap <silent> gi <Plug>(coc-implementation)						" Go to implementation
nmap <silent> gr <Plug>(coc-references)							" Go to references
nmap <F2> <Plug>(coc-rename)								" Enable F2 as rename variable
xmap <leader>f <Plug>(coc-format-selected						" Enable \f to format selected region
nmap <leader>f <Plug>(coc-format-selected)						" Enable \f to format selected region
nnoremap <silent> <space>a  :<C-u>CocList diagnostics<cr>				" Show all diagnostics
nnoremap <silent> <space>e  :<C-u>CocList extensions<cr>				" Manage extensions
nnoremap <silent> <space>c  :<C-u>CocList commands<cr>					" Show commands
nnoremap <silent> <space>o  :<C-u>CocList outline<cr>					" Find symbol of current document
nnoremap <silent> <space>s  :<C-u>CocList -I symbols<cr>				" Search workspace symbols
nnoremap <silent> <space>j  :<C-u>CocNext<CR>						" Do default action for next item.
nnoremap <silent> <space>k  :<C-u>CocPrev<CR>						" Do default action for previous item.
nnoremap <silent> <space>p  :<C-u>CocListResume<CR>					" Resume latest coc list
inoremap jk <ESC>									" Set jk to work as Esc
nmap <C-e> :NERDTreeToggle<CR>								" Set Ctrl e as NERDTree Toggler
vmap ++ <plug>NERDCommenterToggle							" Set ++ to comment current line
nmap ++ <plug>NERDCommenterToggle							" Set ++ to comment current line
```

##### settings.vim

```vim
set relativenumber									" Enable line numbers on left	
set smarttab										" Smart tabs
set cindent										" Smart indentation
set tabstop=4										" Use 4 size tabs
set shiftwidth=4									" Use 4 size tabs
set clipboard=unnamedplus								" Make yank copy to clipboard

" Close vim if the only open buffer is NERDTree
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
```

##### init.vim

Neovim only reads the `init.vim` file, so in order to make all the other files we've created to organize the settings, we have to source them in the `init.vim`. To make this, you should use the keyword `source` follwed by the absolute path to each of the files. Examples below.

**Windows**

```vim
source C:\Users\{username}\AppData\Local\nvim\plugins.vim 		" Sourcing plugins 
source C:\Users\{username}\AppData\Local\nvim\keymaps.vim		" Sourcing keymaps
source C:\Users\{username}\AppData\Local\nvim\settings.vim		" Sourcing settings 
```

**Linux and MacOS**

```vim
source ~/.config/nvim/plugins.vim					" Sourcing plugins
source ~/.config/nvim/keymaps.vim					" Sourcing keymaps
source ~/.config/nvim/settings.vim					" Sourcing settings
```

### Git Configuration

<p align="center"><em><small><a href="#contents">Missclicked? Go back!</a></small></em></p>

```bash
git config --global user.name "Your Username"
git config --global user.email "your@email.com"
git config --global core.editor "nvim -w"
git config --global merge.cool "nvim"
```
