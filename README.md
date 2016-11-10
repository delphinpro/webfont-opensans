# Open Sans web font

Подготовленный шрифт для подключения директивой `@font-face`.
Файлы сконвертированы сервисом
[fontsquirrel.com](http://www.fontsquirrel.com/tools/webfont-generator)
с опцией "Custom Subsetting...", включая наборы "Cyrillic" и "English" и отдельный символ "₽".
Подробные настройки прилагаются в файле [generator_config.txt](./generator_config.txt).

Данный пакет предполагает установку менеджером [bower](https://bower.io/)
и использование с препроцессором SCSS. Содержит миксин, подключающий один вариант шрифта.
Миксин принимает 4 параметра:

* **$weight** - вес шрифта (доступные веса: 300, 400, 600, 700, 800);
* **$style** - начертание (normal, italic);
* **$bower_components: '/bower_components'** - url до папки в которую bower скачивает пакеты;
* **$name: 'Open Sans'** - имя шрифта, задано по умолчанию, обычно менять не требуется.

## Установка

```bash
bower install --save git://github.com/delphinpro/webfont-opensans.git
```

## Подключение

```scss
$bowerComponentsPath: '../bower_components';
@import "./bower_components/webfont-opensans/webfont.mixin";
@include addOpenSansFont(400, normal, $bowerComponentsPath, 'Open Sans');
@include addOpenSansFont(400, italic, $bowerComponentsPath, 'Open Sans');
@include addOpenSansFont(700, normal, $bowerComponentsPath, 'Open Sans');
@include addOpenSansFont(700, italic, $bowerComponentsPath, 'Open Sans');
```

## Использование

```css
.anything {
    font-family: 'Open Sans', sans-serif;
    font-weight: 700; /* or bold */
    font-style: italic;
}
```
