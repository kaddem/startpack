# Startpack Gulp 4.0

Pug, less

Клонируем в текущую папку (точка в конце через пробел):
```
$ git clone git@github.com:kaddem/startpack.git .
```

Избавляемся от привязки к удаленному репозиторию:
```
git remote rm origin
```

Ставим зависимости:
```
npm install --save-dev
```

## Запуск

Gulp 4 ставится локально. Для запуска проекта:
```
npm run gulp
```

## Создаем новые БЭМ блоки

Находясь в корне проекта:
```
$ node newBlock.js blockName blockName2
```

Создаются папки по имени блоков с вложенными одноименными pug и less файлами
```
src/blocks/{blockName}/blockName.pug
src/blocks/{blockName}/blockName.less
```

В диспетчере подключений pug прописываются инклюды созданных БЭМ блоков
```
src/pug/connect/_blocks.pug
```

В диспетчере подключений less прописываются импорты Less файлов созданных БЭМ блоков
```
src/less/style.less
```

### Важно!
При физическом удалении папки блока с диска, подключения этих блоков в style.less и _blocks.pug не удалаются. Удалить их вручную и перезапустить сборку.

## Структура папок и файлов
```
project
├───src
│   ├───blocks
│   │   └───blockName
│   │       ├───blockName.html
│   │       └───blockName.less
│   │
│   ├───html
│   │   ├───common
│   │   │   ├───_head.html
│   │   │   └───_scripts.html
│   │   │
│   │   ├───pages
│   │   │   ├───index.html
│   │   │   └───etc.
│   │   │
│   │   └───template
│   │       ├───_header.html
│   │       ├───_header_index.html
│   │       ├───_footer.html
│   │       └───etc.
│   │
│   ├───less
│   │   ├───common
│   │   │   ├───_grid.less
│   │   │   ├───_fonts.less
│   │   │   ├───_png-sprite.less
│   │   │   ├───_variables.less
│   │   │   └───etc.
│   │   │
│   │   ├───vendor
│   │   │   ├───normalize.css
│   │   │   └───bootstrap
│   │   │
│   │   ├───mixin
│   │   │   ├───_clearfix.less
│   │   │   └───etc.
│   │   │
│   │   └───style.less (диспетчер подключений .less файлов)
│   │
│   ├───scripts
│   │   ├───vendor
│   │   │   ├───jQuery.js
│   │   │   └───etc.js
│   │   │
│   │   └───scripts
│   │       └───myscript.js
│   │
│   └───sprite
│       ├───png
│       │   ├───icon-1.png
│       │   └───icon-2.png
│       │
│       ├───png@2
│       │   ├───icon-1@2.png
│       │   └───icon-2@2.png
│       │
│       └───png@3
│           ├───icon-1@3.png
│           └───icon-2@3.png
│
└───www
    ├───fonts
    │   ├───font.woff2
    │   ├───font.woff
    │   └───font.ttf
    │
    └───img
        ├───images1.jpg
        └───images2.png
```