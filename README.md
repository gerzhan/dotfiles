# Gerzhan | Dotfiles

[github.com/gerzhan/dotfiles](https://github.com/gerzhan/dotfiles.git)

## Инструкция

- установить [GNU Stow](https://www.gnu.org/software/stow/)

```bash
$brew install staw
```

- скопировать репозиторий в домашнюю директорию пользователя

```bash
$cd ~
$git clone https://github.com/gerzhan/dotfiles.git
```

- `ОПЦИОНАЛЬНО` скопировать текущие файлы конфигурации в директорию `./backup`

- `ОПЦИОНАЛЬНО` перенести текущие файлы конфигурации в директорию `dotfiles`

```bash
$cd ~
$mv .gitconfig dotfiles/git/
```

- создать `symlinks` на скопированный файлы конфигурации

```bash
$cd ~/dotfiles
# полностью директорию
$stow -R -v -t ~ .
# из директорий
$stow bash
$stow uzbl
$stow nvim
```

```bash
$stow --help
OPTIONS:
-R — удалить ссылку, если она существует, и создать новую (не удаляя файлы);
-v - показать детали выполнения;
-t — указать цель (~ — домашний каталог пользователя).
```

- при необходимости уточнить [игнорируемые GNU Stow файлы](https://www.gnu.org/software/stow/manual/stow.html#Ignore-Lists) в `.stow-local-ignore`

- проверка ссылок на файлы конфигурации

```bash
$ls -ld
```

## Архитектурный подход

| Sys config     | dotfile structure (stow)     | Apps   |
| -------------- | ---------------------------- | ------ |
| ~/.tmux.conf   | ~/dotfiles/tmux/.tmux.conf   | Tmux   |
| ~/.zshrc       | ~/dotfiles/zsh/.zshrc        | ZSH    |
| ~/.config/nvim | ~/dotfiles/nvim/.config/nvim | NeoVIM |

## TODO

- **Smassh** is a TUI based typing test application inspired by MonkeyType [github.com/kraanzu/smassh](https://github.com/kraanzu/smassh)
