# Gulppack. Версия с Pug + SCSS

## Особенности
* сборка предназначена для автоматизации задач в повседневной front-end разработке;
* автоматическая перезагрузка страницы в браузере с использованием ```browser-sync```;
* использование препроцессора [Pug](https://pugjs.org/api/getting-started.html);
* использование препроцессора [SCSS](https://pugjs.org/api/getting-started.html);
* использование транспайлера [Babel](https://babeljs.io/) для поддержки современного JavaScript (ES6) в браузерах.

## Установка
Установите [Yarn](https://yarnpkg.com/en/docs/install).

> Yarn - это современная альтернатива npm. Yarn работает с тем же файлом ```package.json``` и так же скачивает необходимые модули в папку ```node_modules```, но делает это намного быстрее.

* скачайте сборку: ```git clone https://github.com/andreyalexeich/gulppack-pug.git```;
* установите ```gulp``` глобально: ```yarn global add gulp-cli```;
* перейдите в скачанную папку со сборкой: ```cd gulppack-pug```;
* введите команду, которая скачает необходимые компоненты для корректной работы нашей сборки, указанные в файле ```package.json```: ```yarn```;
* введите команду: ```yarn run dev``` (режим разработки);
* чтобы окончательно завершить проект, введите команду ```yarn run build```.

Если вы всё сделали правильно, у вас должен открыться браузер с локальным сервером и работающим ```browser-sync```.

## Плагины

* [browser-sync](https://browsersync.io/docs/gulp) - живая перезагрузка веб-страницы при внесении изменений в файлы вашего проекта;
* [browserify](http://browserify.org/) - использование ```require``` в браузере и проводить сборку зависимостей;
* [babelify](https://github.com/babel/babelify) - транспайлер [Babel](https://babeljs.io/) для ```browserify```;
* [watchify](https://github.com/browserify/watchify) - отслеживание изменений для ```browserify```;
* [eslint](https://eslint.org/) - линтер для JS-файлов;
* [gulp-autoprefixer](https://www.npmjs.com/package/gulp-autoprefixer) — автоматически расставляет вендорные префиксы в CSS в соответствии с сервисом [Can I Use](https://caniuse.com/);
* [gulp-babel](https://www.npmjs.com/package/gulp-babel) - использование ES6 с [Babel](https://babeljs.io/);
* [gulp-uglify](https://www.npmjs.com/package/gulp-uglify) — минификация JS-файлов;
* [gulp-pug](https://www.npmjs.com/package/gulp-pug) — компиляция Pug в HTML;
* [gulp-sass](https://www.npmjs.com/package/gulp-sass) — компиляция SCSS в CSS;
* [gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css) — минификация CSS-файлов;
* [gulp-sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps) - карта стилей;
* [gulp-rename](https://www.npmjs.com/package/gulp-rename) — переименование файлов, добавление суффиксов и префиксов (например, добавление суффикса ```.min``` к минифицированным файлам);
* [gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin) — сжатие изображений PNG, JPG, GIF и SVG (включая дополнительные плагины для оптимизации);
* [gulp-favicons](https://github.com/evilebottnawi/favicons) — генератор фавиконок для вашего проекта;
* [gulp-if](https://www.npmjs.com/package/gulp-if) - запуск заданий только тогда, когда это нужно;
* [gulp-svg-sprite](https://www.npmjs.com/package/gulp-svg-sprite) — создание SVG-спрайтов;
* [gulp-replace](https://www.npmjs.com/package/gulp-replace) - замена строк;
* [gulp-plumber](https://www.npmjs.com/package/gulp-plumber) — оповещения в командной строке (например, ошибки в SCSS/Sass);
* [gulp-debug](https://www.npmjs.com/package/gulp-debug) — отладка в терминале;
* [gulp-watch](https://www.npmjs.com/package/gulp-watch) — отслеживание изменений в ваших файлах проекта;
* [gulp-clean](https://www.npmjs.com/package/gulp-clean) — удаление файлов и папок;
* [yargs](https://www.npmjs.com/package/yargs) - получение аргументов командной строки в Node.js.

## Файловая структура

### Исходники
* Pug-файлы находятся в папке ```src/views```
	* компоненты (кнопки, инпуты, чекбоксы и т.д.): ```src/views/components```
	* основные компоненты (шапка и футер): ```src/views/modules```
	* секции: ```src/views/sections```
	* миксины: ```src/views/utils```
* SCSS-файлы находятся в папке ```src/styles```
	* стили компонентов (кнопки, инпуты, чекбоксы и т.д.): ```src/styles/components```
	* стили основных компонентов (шапка и футер): ```src/styles/modules```
	* стили секций: ```src/styles/sections```
	* переменные, миксины, наследуемые свойства, стили шрифтов: ```src/styles/utils```
	* сторонние библиотеки (от других разработчиков): ```src/styles/_libs.scss```
* JS-файлы находятся в папке ```src/js```
	* сторонние библиотеки (от других разработчиков): ```src/js/libs.js```
* Изображения находятся в папке ```src/img```
	* векторные изображения для создания спрайтов: ```src/img/svg```
	* единичное изображение для генерации фавиконок находится в ```src/img/favicon.png``` (данное изображение может иметь формат ```.jpg```, ```.png``` или ```.gif``` и размер не менее чем ```100px x 100px```)
* Конфигурационный файл веб-сервера Apache с настройками [gzip](https://habr.com/ru/post/221849/) (сжатие без потерь): ```src/.htaccess```

### Готовые файлы
* скомпилированные HTML-файлы находятся в папке ```dist/```;
* минифицированные CSS-файлы находятся в папке ```dist/styles```;
* минифицированные JS-файлы с поддержкой ES6 находятся в папке ```dist/js```;
* сжатые изображения находятся в папке ```dist/img```.

## Сборка проекта в режиме разработки
```yarn run dev```

## Окончательная сборка
```yarn run build```

## Bower?
Вместо [Bower](https://bower.io/) используйте Yarn или NPM вместе с [Browserify](http://browserify.org/). Например, чтобы подключить jQuery и итог вместе с Вашим кодом собрать в
бандл, необходимо перед запуском ```yarn run dev``` или ```yarn run build```:
* скачать библиотеку: ```yarn add jquery```;
* в ```src/js/main.js``` написать:

```javascript
const $ = require("../../node_modules/jquery/dist/jquery");

$(document).ready(function() {
    $("body").css({background: "#ececec"});
});
```

В результате вы получите последнюю версию jQuery из NPM, которая будет скачана в папку ```node_modules``` в корневой директории проекта. Объект jQuery экспортируется в локальную
переменную ```const $``` вместо глобальной в ```window```, что особо удобно, если скрипт должен работать на сторонних сайтах, где уже может быть (или не быть) установлен jQuery
другой версии.

## Нужен SCSS без Pug?
Используйте [эту](https://github.com/andreyalexeich/gulppack-scss/) сборку.