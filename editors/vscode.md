# VS Code

Дополнительная литература:
1. https://medium.com/p/7f1a26806522
2. https://medium.com/p/8e4939bb1492

из консоли запускаем:
```
code .
code <file>
```

## Комбинации клавиш

Ctrl + K + S - интерактивная подсказка + можно менять комбинации клавиш
Ctrl + K + R - подсказка по клавишам PDF
F1 / Ctrl + Shift + P - Command palette
Ctrl + P (удобное открытие в другой вкладке)
Ctrl + W - закрываем окно
Ctrl + R - переключаемся между проектами
Gtrl + , - настройки

## Bars

Toggle Activity Bar
Ctrl + B - on/off
Ctrl + Shift + E - explorer
Ctrl + Shift + F - find
Ctrl + Shift + G - source control
Ctrl + Shift + D - debug
Ctrl + Shift + X - eXtension

## Вкладки

Ctrl + Tab
Ctrl + PgUp, PgDn

## Оформление

- (ставим) Slime Theme -
  Отключаем статус бар - минимум шума на экране
  Open Editors Visible: 9 -> 0
  Activity Bar
  MiniMap - выглядит круто, но зачем?

## Fonts

https://github.com/IBM/plex

- (ставим) Sublime Text Keymap - чтобы не переучиваться на новые клавиши

## Работа с файлам

- в дереве файлов
- Ctrl + N
- patbenatar.advanced-new-file, Ctrl + Alt + N - выбор папки, создание файла
- stefen leistner file utils, Ctrl + Shift + P - file dublicate, rename, delete, copy path name etc + new file relative current dir
- ben mewburn intelephense
- Ctrl + Shift + O (go to symbol) - позволяет видеть структуру файла - методов
- Ctrl -/+ - шрифт меньше/больше

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

Ctrl + `- открыть терминал
Gtrl + J - скрыть/открыть окно
Ctrl + Shift + C - открыть внешний терминал
Выделенный текст -> Ctrl + Shift + P -> "run selected text"

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

## Multi Cursors

- Alt + Click
- Ctrl + D - выделяем по одному
- Ctrl + Shift + L - выделяет все сразу (в сублайме + G, можно поменять на ...)

## 15 PHP Full Workflow

Settings -> "open files in new window" -> on

## 16 Javascript

- (устанавливаем) Vetur
- (устанавливаем) Import Cost wix - показывает размеры библиотек (у меня не заработало...)
https://medium.com/wix-engineering/keep-your-bundle-size-under-control-with-import-cost-vscode-extension-5d476b3c5a76
- (устанавливаем) Eslint Dirk Baeumer, требуется настройка файла `.eslint.rc`, добавление записей в настройки `eslint.validate`