# VS Code settings

## Font
* [Fira code](https://github.com/tonsky/FiraCode)


## Extensions

Copy the code block below and past into vscode terminal.

```shell
code --install-extension alexcvzz.vscode-sqlite
code --install-extension christian-kohler.path-intellisense
code --install-extension christian-kohler.npm-intellisense
code --install-extension zignd.html-css-class-completion
code --install-extension shamanu4.django-intellisense
code --install-extension pkief.material-icon-theme
code --install-extension esbenp.prettier-vscode
code --install-extension dbaeumer.vscode-eslint
code --install-extension eamodio.gitlens
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension msjsdiag.debugger-for-chrome
code --install-extension editorconfig.editorconfig
code --install-extension kamikillerto.vscode-colorize
code --install-extension morgan-codes.morgan-codes-vscode-theme
code --install-extension ms-python.python
code --install-extension ms-dotnettools.csharp
code --install-extension vscjava.vscode-java-pack
code --install-extension coenraads.bracket-pair-colorizer-2
code --install-extension oderwat.indent-rainbow
code --install-extension shd101wyy.markdown-preview-enhanced
code --install-extension wix.vscode-import-cost
```

> **NOTE:** if you're using vscode insiders, refer to [code-insiders.md](./code-insiders.md) for quick extensions installation.

## Settings 

This will bootstrap theme, and custom configurations that i use on a day to day basis.

```json
{
    "workbench.colorTheme": "morgan.codes",
    "workbench.colorTheme": "morgan.codes",
    "editor.codeActionsOnSave": {
        "source.eslint.fixAll": true
    },
    "editor.fontFamily": "Fira Code",
    "editor.fontLigatures": true,
    "editor.cursorStyle": "line",
    "editor.suggestSelection": "first",
    "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
    "workbench.iconTheme": "material-icon-theme"
}
```

## Git configuration

```
    git config --global user.name "Willians Faria"
    git config --global user.email "williansfaria@hotmail.com"
    git config --global core.editor "code-insiders -w"
    git config --global merge.tool "code-insiders"
```