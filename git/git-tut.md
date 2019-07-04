# Git Tutorial

```
git init
git status

git checkout hello.html // отмена изменений
git add hello.html // индексируем изменения

git commit -m "First Commit" // записываем (сохраняем) в репозиторий
git commit --amend -m "Add an author/email comment" // меняем пред коммит на новый
git reset // сброс всего
git reset HEAD hello.html // сброс выбранного файла, но он остается в каталоге (здесь удаляем checkout)

git commit // открой редактор по умолчанию, для сохранения описания

// ОТМЕНА С СОХРАНЕНИЕМ ИСТОРИИ
git revert HEAD // отмена коммита (вариант №1 безопасный) в редакторе
git revert HEAD --no-edit // отмена без редактора, описание сформирует автоматически

// Второй вариант удаления (у меня не сработал!?)
git reset --hard (hash|tag) // ветки находятся в репозитории, но выброшены из МАСТЕРа

git log // получение списка произведенных изменений
git show <HASH> // просмотр изменений, хэш полный или 7 символов

git checkout <HASH> // перемещение между коммитами (в т.ч. для создания ответвлений)
git checkout master

// ПЕРЕМЕЩЕНИЕ ФАЙЛОВ
// ** вариант 1
git mv hello.html lib

// ** вариант 2
git add lib/hello.html
git rm hello.html

git commit -m "Moved hello.html to lib"// зафиксируем

// РАБОТА С ТЭГАМИ
git tag // просмотр тэгов
git tag v1 // создание тэгов
git tag -d v1 // удаление тэга
git checkout v1 // переключиться на тэг (вместо хэша)
git checkout v1~1 // переключиться на 1 вниз от v1 
git hist master --all // покажет всю историю, не зависимо от того, в каком месте мы, HEAD показывает в каком мы месте

// РАБОТА С ВЕТКАМИ
git branch new-feature // создание новой ветки
git branch // показать ветки и какая текущая
git checkout new-feature // переключение на новую ветку
```

## Каталог .git

Структура папок:
- `.git/objects` - Имена каталогов являются первыми двумя буквами хэша sha1 объекта, хранящегося в git.
- `.git/config` - Это файл конфигурации, создающийся для каждого конкретного проекта. Записи в этом файле будут перезаписывать записи в файле .gitconfig вашего главного каталога, по крайней мере в рамках этого проекта.
- `.git/refs/tags` - Каждый файл соответствует тегу, ранее созданному с помощью команды git tag. Его содержание – это всего лишь хэш коммита, привязанный к тегу.
- `.git/refs/heads` - Каталог heads практически аналогичен, но используется для веток, а не тегов. На данный момент у нас есть только одна ветка, так что все, что вы увидите в этом каталоге – это ветка master.
- `.git/HEAD` - Файл HEAD содержит ссылку на текущую ветку, в данный момент это должна быть ветка master.

Исследуйте git репозиторий вручную самостоятельно. Смотрите, удастся ли вам найти оригинальный файл hello.html с самого первого коммита вручную по ссылкам SHA1 хэша в последнем коммите.
https://githowto.com/ru/git_internals_working_directly_with_git_objects

## git log

```
git log -p // Лог с дифами
git log --pretty=oneline
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
```

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