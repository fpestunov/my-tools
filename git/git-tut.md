# Git Tutorial

git init
git status

git checkout hello.html // отмена изменений
git add hello.html // индексируем изменения

git commit -m "First Commit" // записываем (сохраняем) в репозиторий
git reset // сброс всего
git reset HEAD hello.html // сброс файла

git commit // открой редактор по умолчанию, для сохранения описания

git revert HEAD // отмена коммита (вариант №1 безопасный) в редакторе
git revert HEAD --no-edit // отмена без редактора

git log // получение списка произведенных изменений

git checkout HASH // перемещение между коммитами (в т.ч. для создания ответвлений)
git checkout master

git tag // просмотр тэгов
git tag v1 // создание тэгов
git checkout v1 // переключиться на тэг (вместо хэша)
git checkout v1~1 // переключиться на 1 вниз от v1 
git hist master --all // покажет всю историю, не зависимо от того, в каком месте мы, HEAD показывает в каком мы месте


## git log

git log --pretty=oneline
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short

- --pretty="..." — определяет формат вывода.
- %h — укороченный хэш коммита
- %d — дополнения коммита («головы» веток или теги)
- %ad — дата коммита
- %s — комментарий
- %an — имя автора
- --graph — отображает дерево коммитов в виде ASCII-графика
- --date=short — сохраняет формат даты коротким и симпатичным

## config

```
// установка имени
git config --global user.name "Your Name"
git config --global user.email "your_email@whatever.com"

// параметры установки окончаний строк Unix/Mac
git config --global core.autocrlf input
git config --global core.safecrlf true

// параметры установки окончаний строк Windows
git config --global core.autocrlf true
git config --global core.safecrlf true

// установка отображения unicode
git config --global core.quotepath off

// установка алиасов
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
git config --global alias.type 'cat-file -t'
git config --global alias.dump 'cat-file -p'
```

## aliases

```
[alias]
  co = checkout
  ci = commit
  st = status
  br = branch
  hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
  type = cat-file -t
  dump = cat-file -p

  gs='git status '
  ga='git add '
  gb='git branch '
  gc='git commit'
  gd='git diff'
  go='git checkout '
  gk='gitk --all&'
  gx='gitx --all'	  
  got='git '
  get='git '  
```

## Настройки

Настройки редактора по умолчанию:
- переменная среды GIT_EDITOR
- параметр конфигурации core.editor
- переменная среды VISUAL
- переменная среды EDITOR

### .gitconfig

```
# This is Git's per-user configuration file.
[user]
# Please adapt and uncomment the following lines:
	name = John Doe
	email = jd@mail.com
[core]
	editor = \"c:\\Sublime3\\sublime_text.exe\" -w
	safecrlf = false
	quotepath = off
[alias]
  co = checkout
  ci = commit
  st = status
  br = branch
  hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
  type = cat-file -t
  dump = cat-file -p

```