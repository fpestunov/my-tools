## VS Code for PHP developers

[Статьи и видео](userguide.md)

=======
# PHP & VSCode

- https://code.visualstudio.com/docs/languages/php
- https://tyapk.ru/blog/post/php-vscode-plugins
- https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner
- https://guides.hexlet.io/vscode-for-php-setup/
- https://tighten.co/blog/configure-vscode-to-debug-phpunit-tests-with-xdebug


## PHP Intelephense
https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client

## Disable basic suggestions

Добавим в `settings.json` строку `"php.suggest.basic": false,`

## Enable autocomplete in comments / annotations

When you write PHP code, a good practice is to add **PHPDoc** annotations to make your code more understandable and to help your IDE provide you with relevant code suggestions. By default, VS Code doesn't suggest anything while writing annotations. To activate code suggestions in comments, open the settings.json file and add the following line:

`"editor.quickSuggestions": { "comments": true },`

## X Debug

1. Install PHP XDebug

- https://xdebug.org/wizard

`php -m` должен показать **XDebug**.

2. Tune up VSCode

- <kbd>Ctrl+Shift+X</kbd>
- `felixfbecker.php-debug`
