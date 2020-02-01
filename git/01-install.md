# Установка и настройка Git

**Установка Git**

- Windows https://git-scm.com/download/win
- Linux Ubuntu `sudo apt-get install git`
- Проверить что, установлено `git --version`

**Настройка Git**

```sh
// без --global настройки Гит будут работать для текущего проекта
git config --global user.name "ваше имя"
git config --global user.email адрес
```

**Устанавливаем SSH-ключи**

Проверяем наличие:
```sh
cd ~/.ssh
ls
// name (private) & name.pub (public)
```

Устанавливаем:
```sh
// генерируем
ssh-keygen -t rsa -b 4096 -C "your_mail@example.com"
// проверяем доступность
eval "$(ssh-agent -s)"
// добавляем путь до ключа
ssh-add ~/.ssh/your_key_name
```

Если вы захотите переименовать ключ, могут возникнуть проблемы. Их можно решить, добавив в  `~/.ssh/config` связь ключа с доменом:
```
Host bitbucket.org
 IdentityFile ~/.ssh/name1
Host github.com
 IdentityFile ~/.ssh/name2
```

**Добавляем SSH-ключи на GitHub**

Добавляем `id_rsa.pub` (public key):
https://github.com/settings/keys

**Проверка работы**

```sh
ssh -T git@github.com
// Hi UserName! You've successfully authenticated, but GitHub does not provide shell access.
```


**Конфигурируем Git**

Изменения попадают в файл `.gitconfig` в домашней папке пользователя.

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

// этот файл защита от коммитов
.gitignore
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