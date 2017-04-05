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
src
├───assets
│   └───bemtopug
│
├───blocks
│   └───blockName
│       ├───blockName.pug
│       └───blockName.less
│
├───fonts
│   ├───font.ttf
│   ├───font.woff
│   └───font.woff2
│
├───pug
│   ├───connect
│   │   └───_blocks.pug
│   │
│   ├───layout
│   │   └───_layoutBase.pug
│   │
│   ├───pages
│   │   └───index.pug
│   │
│   └───template
│       ├───_head.pug
│       ├───_header.pug
│       └───_footer.pug
│
├───less
│   ├───common
│   │   ├───_grid.less
│   │   ├───_fonts.less
│   │   ├───_png-sprite.less
│   │   └───_variables.less
│   │
│   ├───vendor
│   │   ├───normalize.css
│   │   └───bootstrap
│   │
│   ├───mixin
│   │   └───_clearfix.less
│   │
│   └───style.less (диспетчер подключений .less файлов)
│
├───js
│   ├───vendor
│   │   ├───jQuery.js
│   │   └───etc.js
│   │
│   └───scripts
│       └───myscript.js
│
└───img
    ├───png-sprite
    │   ├───file1.png
    │   └───file2.png
    │
    ├───images1.jpg
    └───images2.png

```