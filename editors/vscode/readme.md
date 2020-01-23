# VS Code



из консоли запускаем:
```
code .
code <file>
```

## Материалы

- https://code.visualstudio.com/docs/getstarted/introvideos
- https://scotch.io/courses/make-visual-studio-code-your-editor
- https://medium.com/p/7f1a26806522
- https://medium.com/p/8e4939bb1492

## Установка и удаление

How to completle remove settings?
- settings `%UserFolder%\AppData\Roaming\Code (%AppData%\Code)`
- extensions `%UserFolder%\.vscode`

After installation:
- disable telemetry and crash reporting 
https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting

## VSCode cata:
- Help / Interactive Playground

## Первоначальные настройки

- F1 -> Toggle Status Bar
- F1 -> Toggle MiniMap
- Open Editors Visible: 9 -> 0 (показывать редактируемые файлы)

### 1. Тема

*Компоненты надо изучать!*

- Nord Theme
- Material Theme
- Vscode-icons


## 2. Fonts

https://github.com/tonsky/FiraCode
https://github.com/tonsky/FiraCode/wiki/VS-Code-Instructions

https://github.com/IBM/plex

- Ctrl -/+ - шрифт меньше/больше

## 3. Работа с файлам


- patbenatar.advanced-new-file
Ctrl + Alt + N - выбор папки, создание файла

- sleistner.vscode-fileutils

F1 ->  file dublicate, rename, delete, copy path name etc + new file relative current dir

## 4. open in browser

techer.open-in-browser


## Комбинации клавиш

**Rule - look actions in command palete first AND memorizy usefull shortcuts**

- <kbd>F1</kbd> / <kbd>Ctrl + Shift + P</kbd> - Command palette

- <kbd>F11</kbd> - весь экран
- <kbd>Gtrl + ,</kbd> - open settings
- <kbd>Ctrl + K + S</kbd> - интерактивная подсказка + можно менять комбинации клавиш
- <kbd>Ctrl + K + R</kbd> - подсказка по клавишам PDF
- <kbd>Ctrl + P</kbd> (удобное открытие в другой вкладке)
- <kbd>Ctrl + W</kbd> - закрываем окно
- <kbd>Ctrl + R</kbd> - переключаемся между проектами

**Другие**

- Ctrl + Shift + O (go to symbol) - позволяет видеть структуру файла - методов

## JS function
- F12 defenition 
- Alt + F12 defenition 

## SELECTION
- Ctrl+D
- Ctrl+Shift+L

## Bars

F1 -> Toggle Activity Bar
Ctrl + B - on/off
Ctrl + 0 - focus into Side bar
Ctrl + Shift + E - explorer
Ctrl + Shift + F - find
Ctrl + Shift + G - source control
Ctrl + Shift + D - debug
Ctrl + Shift + X - eXtension

## Вкладки

Ctrl + Tab
Ctrl + PgUp, PgDn
CTRL + \ - split editor right (текущий файл на 2 экрана)

# Working with text

- Дублирование строк
- Перемещение строк

Ctrl + / - Line comment
Alt + Shift + A - Block comment

## Multi Cursors

- Ctrl + Alt + Up/Down - Add cursor above/below
- Alt + Click
- Ctrl + D - выделяем по одному
- Ctrl + Alt D - выделяем по одному (вверх)
- Ctrl + Shift + L - выделяет все сразу (в сублайме + G, можно поменять на ...)

## vim

vscodevim.vim
see vim mastery

## Snippets

Ctrl + Shift + P -> snippets configure -> PHP

- можно писать вручную, а можно...
- (установим) snippet-creator nikita kunevich, пишем код, и добавляем сниппет через ком-панель
- "tab compl"->true
  https://code.visualstudio.com/docs/editor/userdefinedsnippets

## terminal

Ctrl + \`- открыть терминал
Gtrl + J - скрыть/открыть окно
Ctrl + Shift + C - открыть внешний терминал
Выделенный текст -> F1 -> "run selected text"

## Git ready

F1 -> "git" и много команд

- работа через интерфейс или консоль
- можно установить для доп возможностей Git Lense

## PHPUnit

-(ставим) better-phpunit

- выделяем метод или класс и запускаем F1 -> phpunit: run
- и делает для этой операции шорткей Ctrl + T

- ! классная вещь, во время правки кода, запускать тесты (не открывая тестов) F1 -> phpunit: run previos

## PHP Formating

- (ставим) PHP CS Fixer junstyle

он работает, если установлен фиксер в системе.

https://github.com/FriendsOfPHP/PHP-CS-Fixer
composer global require friendsofphp/php-cs-fixer
composer.phar global update friendsofphp/php-cs-fixer
$ php php-cs-fixer.phar fix /path/to/dir
$ php php-cs-fixer.phar fix /path/to/file

cs-fixer сложноват и не чистит $a=1;
он конкурировал с другим фиксером!
Но, можно сделать отдельный файл, с личными настройками и указать на него путь.

он конкурировал с другим фиксером!

## Context Menu

Вместо мышки используем клавиатуру.

Ctrl + Shift + S -> context -> новая комбинация Alt + Enter

## Sweet Sweet PHP debugging

Статья про установку:
https://tighten.co/blog/configure-vscode-to-debug-phpunit-tests-with-xdebug

Устанавливаем:
https://xdebug.org/docs/install

Вот для виндоус:
https://xdebug.org/wizard.php

`php -m` смотрим установленные модули

Это поддержка PHP:
https://php.net/supported-versions.php

- (устанавливаем) PHP Debug plugin felix baker

Ct + Sh + D -> PHP

## 15 PHP Full Workflow

- ben mewburn intelephense

Settings -> "open files in new window" -> on

## 16 Javascript

- (устанавливаем) Vetur
- (устанавливаем) Import Cost wix - показывает размеры библиотек (у меня не заработало...)
https://medium.com/wix-engineering/keep-your-bundle-size-under-control-with-import-cost-vscode-extension-5d476b3c5a76
- (устанавливаем) Eslint Dirk Baeumer, требуется настройка файла `.eslint.rc`, добавление записей в настройки `eslint.validate`
