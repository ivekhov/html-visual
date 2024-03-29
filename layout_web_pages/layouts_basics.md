# Основы верстки страниц. Введение

Полезный ресурс для проверки кода:
https://codepen.io/pen/tour/welcome/start 

Описание работы тегов:
https://ru.hexlet.io/courses/css-content/lessons/box-model/theory_unit

CSS:
https://css-live.ru/articles-css/udivitelnyj-i-neizvestnyj-inline-block.html

Код цветов:
https://htmlcolorcodes.com 

## padding 
Делает отступы внутри элемента, тем самым увеличивая его в размерах

```css
.element {
  padding: 10px 20px 30px 40px;
}

/* Эквивалентно записи */

.element {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding-left: 40px;
}
```

Свойство ```padding``` может принимать несколько разных вариаций сокращенных записей:

- Одно значение — устанавливает одинаковый отступ по всем сторонам сразу. Например, ```padding```: 20px установит внутренний отступ в 20px сверху/справа/снизу/слева

- Два значения — устанавливает отступы по вертикали и горизонтали. Например, padding: 20px 30px установит внутренний отступ в 20px сверху/снизу и 30px справа/слева

- Три значения — устанавливает отступы сверху, по горизонтали и снизу. Например, padding: 20px 30px 40px установит внутренний отступ в 20px сверху, 30px справа/слева и 40px снизу


Cвойства, которые отвечают за ширину и высоту блока:

- Внутренние отступы. В CSS за их установку отвечает свойство ```padding```

- Границы, устанавливающиеся свойством ```border```
`
- Внешние отступы. За них отвечает свойство ```margin```

- Высота и ширина блока, устанавливаемые свойствами ```height``` и ```width```

## margin

устанавливает внешние отступы

Свойство margin не влияет на видимые размеры элементов, но на место отступов не смогут встать другие элементы, поэтому оно входит в формирование общего размера.

## Границы

Видимые границы элемента можно задать одним из двух свойств:
```
- border
- outline
```
Различие свойств в поведении:

- border прямо влияет на блочную модель и размеры элемента
- outline рисует границу «поверх» элемента и не влияет на его размеры

Их синтаксис похож, поэтому разберем только свойство ```border```, которое является обобщенным для трех свойств:

- border-width — ширина границы
- border-style — тип границы
- border-color — цвет границы

## Display

Для изменения типа отображения элемента используется свойство ```display```. В качестве значения принимается тип отображения элемента: блочный, строчный, flex-контейнер, с которым вы скоро познакомитесь, и множество других значений. В этом уроке остановимся на трех:

- block
- inline
- inline-block

## Стили текста

## Цвет текста

Атрибут ```color```.


Для выравнивания текста используется свойство ```text-align```, которое принимает следующие значения:

- left — выравнивание текста по левому краю. Это значение устанавливается по умолчанию.
- center — выравнивание текста по центру.
- right — выравнивание текста по правому краю.
- justify — выравнивание текста по ширине. Данное значение выравнивает текст так, чтобы поместить слова строго от начала блока до его конца. При этом возможны изменения размеров пробелов между словами.


## Насыщенность текста

Используя CSS можно гибко настраивать насыщенность шрифта. Насыщенность используется для выделения важного участка текста и придает ему «вес» относительно соседних элементов. Для управления насыщенностью в CSS используется правило ```font-weight```. Оно принимает следующие значения:

- Значения от 100 до 900 с шагом 100
- ```lighter``` — сверхтонкое начертание. Делает текст менее насыщенным, чем текущее значение
- ```normal``` — значение по умолчанию. Соответствует числовому значению 400
- ```bold``` — жирное начертание текста. Соответствует числовому значению 700
- ```bolder``` — сверхжирное начертание. Делает текст насыщеннее, чем текущее значение

## Размер текста

Управлять размером текста можно с помощью свойства ```font-size```. Текст с большим размером шрифта первым бросается в глаза, поэтому заголовки, помимо выравнивания по центру, имеют больший размер шрифта.

## Шрифты

## Семейство шрифтов

Если указано несколько шрифтов, то браузер будет считывать их слева направо до первого шрифта, который он сможет использовать. Остальные шрифты будут игнорироваться. Свойство ```font-family```.

Все шрифты можно разделить на три большие группы:

- Антиква или шрифты с засечками. Такие шрифты чаще всего используются в книгах и новостных сайтах. В CSS обозначается ```serif```.
- Гротеск или шрифты без засечек. Основной тип шрифтов на сайтах. Прямо сейчас вы читаете именно такой шрифт. В CSS обозначается ```sans-serif```.
- Моноширинный шрифт. У этого семейства все символы имеют одинаковую ширину. Вы можете увидеть такой шрифт в терминалах или редакторах кода. В CSS обозначается ```monospace```.

## Установка шрифта

Для установки шрифта используется конструкция ```@font-face```. Она позволяет подключить шрифт в различных расширениях, определить имя и путь к файлу. На примере шрифта Roboto воспользуемся такой конструкцией.

Пусть наш проект имеет директорию fonts/, внутри которой находятся файлы шрифтов.
```
project/
├── css/
│   └── style.css
├── fonts/
│   │── Roboto-Regular.ttf
│   │── Roboto-Bold.ttf
│   └── Roboto-Light.ttf
```

Хорошим тоном является указание @font-face в самом начале CSS файла, а не перед первым использованием шрифта. Это позволит правильнее структурировать CSS. Есть два основных свойства, которые принимает @font-face:

- ```font-family``` — Имя подключаемого шрифта. Именно по нему можно обратиться после подключения.
- ```src``` — Путь к файлу со шрифтом.

Пример:
```css
@font-face {
  font-family: "Roboto Regular";
  src: url("../fonts/Roboto-Regular.ttf");
}

body {
  font-family: "Roboto Regular", sans-serif;
}
```

## Стиль шрифта

свойство ```font-style```, которое может принимать одно из трех значений:

- ```normal``` — стандартное значение. Соответствует нормальному отображению шрифта. Именно такой стиль вы читаете прямо сейчас.
- ```italic``` — курсивное начертание. Данное начертание имеет наклонные буквы, в отличие от нормального стиля. Вот так выглядит курсивный шрифт.
- ```oblique``` — тоже курсивное начертание. Зачастую оно не отличается от значения italic.

Курсив, который задается значением italic, является самостоятельным шрифтом, для которого есть отдельный файл в системе или на сервере. Он относится больше к рукописному тексту, тогда как oblique искусственно наклоняет символы текущего шрифта.

## Строчные символы

Капитель — вид строчных букв, размер которых совпадает (или приближен) к размеру заглавных букв. Такой прием используется в дизайне в виде стилистического оформления. 

Устанавливается с помощью свойства ```font-variant```. У него возможны два значения:
- ```normal``` — стандартная стилистика строчных символов.
- ```small-caps``` — капитель.

## Межстрочный интервал

свойство ```line-height```. Оно может принимать значения с различными единицами измерения. Чаще всего используют число, указывающее, во сколько раз интервал больше размера шрифта.

## Приоритетность правил

Обобщенное свойство ```font``` перебивают отдельные font-size, line-height и так далее. Если в коде вы указали ```font-variant: small-caps;```, а потом для этого же элемента применили ```font: 16px/24px sans-serif;```, то капитель будет сброшена в значение по умолчанию.


```
font-style
font-variant
font-weight
font-size
line-height
font-family
```
## Списки и стилизация

- Маркированные
- Нумерованные
- Списки определений

**Определения и каталоги**

```html
Тег <dl></dl>, внутри которого не привычная схема <li></li>, а система из двух тегов:

<dt></dt> — термин;
<dd></dd> — определение.


<dl>
    <dt>HTML</dt>
    <dd>Язык гипертекстовой разметки</dd>
    <dt>CSS</dt>
    <dd>Каскадные таблицы стилей</dd>
</dl>
```
**Маркер**

изменение маркера, который появляется в левой части пункта списка. В маркированных и нумерованных списках его можно изменить с помощью свойства list-style-type
Изменять маркер можно одним из двух способов:
- Установка свойства на контейнер. В этом случае все элементы списка получат тот маркер, который был указан в свойстве.
- Установка свойства на элемент списка. Маркер изменится только у одного пункта списка, другие получат маркер по умолчанию.

```css
.list-style-square {
    list-style-type: square;
}

.list-style-none {
    list-style-type: none;
}
```

**Картинки в качестве маркеров**

Чтобы установить маркер в виде своего изображения, используется свойство list-style-image, значением которого является ссылка на изображение. Оно указывается внутри url()
```css
.list-image {
  list-style-image: url("./good.png");
}
```

## Колонки

информация внутри колонок обрабатывается «как есть». Это значит, что все отступы сохраняются. В случае с параграфами стоит сбрасывать верхний отступ. Это позволит держать первый параграф на одной линии с другими колонками

```html
<article class="columns-2">
    <p>
        Lorem ...</p>
    <p>
        Ipsum ...
    </p>
</article>
```
```css
.columns-2 p {
  margin-top: 0;
}
```
Ширина колонок - 
column-width — с его помощью задается оптимальная ширина колонок. Слово «оптимальная» является главным. В отличие от свойства width, здесь не устанавливается четкая ширина, и, если места в контейнере хватает, то колонки будут растягиваться на всю доступную ширину.

```css
.columns-2 {
  columns: 250px 2;
}

/*or that*/
.columns-2 {
    column-count: 2;
    column-width: 250px;
}
```

### Отступы между колонками

По умолчанию расстояние между колонками равно 1em. Единица измерения em отсчитывается от размера шрифта. Если размер шрифта равен 16 пикселям, то и 1em равен 16 пикселям

Задать отступы между колонками можно с помощью свойства column-gap

```css
.columns-2 {
  columns: 250px 2;
  column-gap: 30px;
}
```

### Границы между колонками

Для создания границы используется свойство column-rule, которое является краткой записью следующих свойств:

- column-rule-width — ширина границы.
- column-rule-style — тип границы. Значения совпадают со значениями свойства border.
- column-rule-color — цвет границы.

- Вы можете указывать как три отдельных свойства, так и краткую запись.

```css
.columns-2 {
  columns: 250px 2;
  column-gap: 30px;
  column-rule: 2px solid black;
}
```

### Добавление контента в несколько колонок

Если представить себе газету, то там не всегда текст идет строго по колонкам. Частая ситуация — заголовок, который накладывается на все колонки, как бы разделяя их по горизонтали.

Для разделения колонок используется свойство column-span. Оно принимает всего два значения:

- none — значение по-умолчанию. Текст находится просто внутри колонок.
- all — текст «выходит из колонки» и разделяет их.

```css
/*пример с внедрением заголовка в центр страницы*/
h2 {
  text-align: center;
  column-span: all;
}

.columns-2 {
  columns: 250px 2;
  column-gap: 30px;
  column-rule: 2px solid black;
}
```

### Перенос колонок

Для запрета такого переноса можно воспользоваться свойством break-inside и запретить перенос внутри данного элемента.

```css
figure {
    border: 1px solid;
    break-inside: avoid;
}
```
## Единицы измерения

https://ru.hexlet.io/courses/css-content/lessons/units/theory_unit


Пиксель - для использования в указании абсолютных размеров объектов.
При этом стоит понимать, что 100 пикселей на одном экране могут быть не равны 100 пикселям на другом экране. Все зависит от размера пикселей в мониторе. А это, в свою очередь, зависит от характеристик экрана и его разрешения.

По этим причинам можно назвать пиксель как относительной, так и абсолютной единицей измерения. Все зависит от того, с какой точки зрения мы смотрим. Для нас важен пиксель в контексте CSS, где он является абсолютной единицей.

Другие абсолютные единицы почти не используются в разработке для веб-устройств. Стоит их перечислить, но есть вероятность, что вы никогда не будете их использовать.

- cm — сантиметры
- mm — миллиметры
- Q — четверть миллиметра
- in — дюйм
- pc — пайка/пика. Термин из типографики
- pt — пункт

## Относительные единицы

Относительные единицы  берут свое значение от других значений. Самой универсальной такой единицей являются проценты. 
Они всегда берут свои значения от ближайшего родительского элемента. Остальные единицы можно разделить на две группы:

1. Относительные единицы, рассчитывающиеся от **размера шрифта**.
2. Относительные единицы, рассчитывающиеся от **размера экрана**. Это немного грубое сравнение — на самом деле расчет ведется от **размера viewport**. О том, что это такое, вы узнаете из курса по адаптивности.

## Размер шрифта в относительных единицах

две основные относительные единицы измерения, которые зависят от размера шрифта: em и rem.

1. Значение em очень похоже на использование процентов. Оно показывает во сколько раз размер будет больше, чем у ближайшего вычисленного значения font-size

2. Второй такой единицей является rem. Ее способ работы точно такой же, как у em. Но есть одно громадное отличие: rem отсчитывается от размера шрифта корневого элемента. Корневым элементом является <html>. Именно размер шрифта у этого элемента и учитывается при расчете единицы rem.

## Относительные единицы, рассчитывающиеся от размера экрана

CSS позволяет задавать размеры относительно текущего размера viewport — размера окна браузера, доступного без прокрутки. Основными двумя единицами являются vw (viewport width) — ширина viewport и vh (viewport height) — высота viewport. Вы можете рассматривать это как процент от размера viewport.

Частый «кейс» с использованием таких единиц — создание секции на всю доступную область браузера.

## Медиаэлементы

Для вставки изображения с помощью HTML используется специальный тег <img>. Это непарный тег, основными атрибутами которого являются:

- src — путь до изображения.
- alt — альтернативный текст изображения. - Лучше формировать полнеое описание на случай, если медиа-контент не загрузится

``<img src="../images/hexlet.png" alt="Логотип Hexlet">``

### src
У изображений, вставленных с помощью тега <img> есть неприятная особенность — они не сжимаются в зависимости от устройства.

```css
img {
  max-width: 100%;
  height: auto;

  vertical-align: middle;
}
```

### Использование нескольких версий изображения
В HTML существует специальная конструкция, которая позволяет использовать разные версии изображений. Это отличная возможность адаптировать изображения для различных устройств. Основное преимущество заключается в том, что в зависимости от разрешения устройства браузер будет загружать определенное изображение

```html
<picture>
  <source
    media="(min-width: 1024px)"
    srcset="https://www.fillmurray.com/1280/500"
  >
  <source
    media="(min-width: 700px)"
    srcset="https://www.fillmurray.com/700/360"
  >

  <img src="https://www.fillmurray.com/500/360" alt="Bill Murray">
</picture>
```

## Видеофайлы

Добавление видео происходит с помощью тега video. Все видеофайлы добавляются 
внутри этого тега с помощью тегов <source>. 
Исключением является ситуация, при которой видеофайл всего один. 
Тогда его можно добавить в виде атрибута для тега ```<video>```.

```<video src="./video/hexlet-presentation.mp4"></video>```

множество интересных атрибутов. Не все из них стоит знать в начале своего пути, но основные из них мы изучим:

- autoplay — Автоматическое воспроизведение видео. Не добавляйте его без крайней необходимости. Всегда хочется показать все лучшее со страницы, но внезапное воспроизведение файла скорее разозлит пользователя
- controls — добавление интерактивных элементов управления, таких как запуск, остановка, регулировка звука
- muted — Выключение воспроизведения аудиодорожки. Если в видео важен только визуальный ряд, а фоновая музыка второстепенна, то стоит установить этот атрибут. При необходимости пользователь сам включит звук
- preload — Указание на предзагрузку видео до взаимодействия с ним. Может принимать одно из нескольких значений:
- metadata — подгрузка метаданных. К ним относится название видео, его длина
- auto — подгружать видео с самого начала. Если видео является обязательным элементом для просмотра (например, после окончания статьи), то вы можете включить подзагрузку. Пока пользователь прочитает статью, видео для него уже будет загружено. Будьте аккуратны, думайте о пользователях с мобильным интернетом
- none — не загружать видео до момента взаимодействия с пользователем
- poster — Ссылка на изображение, которое будет использовано в виде превью видео

## Аудиофайлы

Процесс вставки аудиофайлов почти не отличается от вставки видеофайла. 
Используя тег ```<audio>``` можно задать как один файл, так и несколько, 
с помощью вложенных тегов ```<source>```.

## Таблицы
Любая таблица начинается с парного тега ```<table>```. Одного этого контейнера уже достаточно, чтобы получить первую работающую таблицу.

В отличие от списков, таблицы можно назвать двухмерной системой. Здесь есть строки и столбцы. Именно в таком порядке они и обозначаются.

Для создания строки используется тег ```<tr>```. Количество строк и регулируется количеством этих тегов внутри ```<table>```.

```html
<table>
<!--    title of table-->
    <caption>
        Профессии
    </caption>
    
    
<!--    header of table-->
    <thead>
    <tr>
        <th>№</th>
        <th>Название профессии</th>
        <th>Описание</th>
    </tr>
    </thead>
    
    
  <tr>
    <td>Строка 1. Колонка 1.</td>
    <td>Строка 1. Колонка 2.</td>
    <td>Строка 1. Колонка 3.</td>
  </tr>
  <tr>
    <td>Строка 2. Колонка 1.</td>
    <td>Строка 2. Колонка 2.</td>
    <td>Строка 2. Колонка 3.</td>
  </tr>
  <tr>
    <td>Строка 3. Колонка 1.</td>
    <td>Строка 3. Колонка 2.</td>
    <td>Строка 3. Колонка 3.</td>
  </tr>
</table>
```

```css
html {
  font-family: sans-serif;
}

table {
  color: #212529;

  border-collapse: collapse;
}

td,
th {
  padding: 0.75rem;

  border-top: 1px solid #dee2e6;
}

th {
  border-bottom: 2px solid #dee2e6;
}

caption {
  margin-top: 25px;

  font-size: 0.7em;
  text-align: right;

  caption-side: bottom;
}

```

```css

table,
td {
    border: 1px solid #000;
    
/*    delete double margins*/
    border-collapse: collapse;
    
/*   content aligning */
    vertical-align: top;
    
    
}
```

Объединение ячеек в таблице

В HTML для этой операции существуют два атрибута:

- colspan — объединение столбцов.
- rowspan — объединения строк.

- Принцип работы достаточно прост — в качестве значения атрибута указывается количество строк/столбцов, которое должен занять элемент

## Формы

```html
<form action="/forms/helper.php">
  <!-- Данные из формы будут отправлены в PHP файл helper, который расположен в директории forms на сервере -->
</form>
```

В HTML для этого используется два тега:

- ```<input>``` — одиночный тег, в котором располагается небольшая информация. Это может быть телефон, email, дата рождения, имя и так далее.
- ```<textarea>``` — парный тег, позволяющий пользователю ввести длинное сообщение. Это могут быть комментарии к заказу, отзыв.

```html
<form>
  <textarea cols="20" rows="10"></textarea>
</form>

```
OR
```css
body {
  padding: 20px;
  font: 18px/1.5 sans-serif;
}

textarea {
  resize: none;
}
```

### input

Input и Label нужно прописывать отдельно.

```html
    <div class="form-input mb-2">
        <label for="name" class="sr-only">Ваше имя</label>
        <input type="text" id="name" placeholder="Ваше имя">
    </div>

    <div class="form-input mb-2">
        <label for="message" class="sr-only">Ваше сообщение</label>
        <textarea id="message" placeholder="Ваше сообщение"></textarea>
    </div>
```

## Селекторы

Выбор соседнего элемента

```css
/*выбор элемента B, который находится непосредственно после элемента A. 
Такой селектор называется смежным или соседним*/

.time + .timer {
}

/*выбор элемента B, который находится на том же уровне 
вложенности, что и A. При этом они имеют общего родителя 
и все элементы B находятся после элемента A в HTML. 
Такой селектор называется родственным.*/

.time ~ .timer {
}

```


## Селекторы по атрибуту

HTML позволяет добавлять любые пользовательские атрибуты и работать с ними. Пользовательскими считаются такие атрибуты, которые мы определяем сами. Их не существует в документациях, спецификациях. Они нужны для разработчиков, чтобы удобнее обращаться к элементам или отделять похожие элементы

```html
<section data-full-screen></section>
```

```css
section[data-full-screen] {
  width: 100vw;
  height: 100vh;

  background: #2196f3;
}
```
В случае большого числа селекторов, называющихся похожим образом, 
используются регулярки в файлах стилей

```css
[data-nm-section^="catalog"] {
/*    */
}
```

- [data-nm-section$="catalog"] — вхождение подстроки в конце значения атрибута.
- [data-nm-section*="catalog"] — вхождение подстроки в любом месте значения атрибута.
- [data-nm-section^="catalog"]  - начинается с 


## Точное указание элемента внутри определенного блока

```css
.articles article h3
```

Подцепление свойства  селекторов системно названых

```css
.articles article h3 + p {
}
```

## Псевдоклассы


Псевдоклассами не выбирается элемент напрямую. Они указывают на какое-либо состояние элемента

Например, состояние объекта в результате действия пользователя

```css
a:hover {
  color: #2196f3;
  text-decoration: none;
}
```

Для других состояний так же существуют свои псевдоклассы.

- :active — Стиль при нажатии на ссылку, но до перехода по ней.
- :visited — Стиль уже посещенной ссылки.
- :focus — Стиль при событии фокуса на элементе.

## Структурные псевдоклассы

К структурным псевдоклассам можно отнести те, которые добавляют стили к элементу в зависимости от его месторасположения внутри HTML. Это мощное средство, позволяющее добиться сложных стилей без использования большого количества классов.
Основным структурным псевдоклассом является :nth-child(условие).
Самое простое — указать конкретный элемент, который нужен. Для этого достаточно указать порядковый номер элемента


Для некоторых стандартных ситуаций существуют специальные псевдоклассы:

- :first-child — выбирает первый элемент внутри родителя.
- :last-child — выбирает последний элемент внутри родителя.
- :first-of-type — выбирает первый элемент внутри родителя, учитывая тип элемента.
- :last-of-type — выбирает последний элемент внутри родителя, учитывая тип элемента.
- :only-child — выбирает элемент, если он единственный внутри родителя.

## Псевдоэлементы

Они могут виртуально создать за нас такой тег и стилизовать его, используя только CSS. Это решает сразу две проблемы, которые были описаны выше:

Нет необходимости проставлять новые теги. Достаточно только указать нужный селектор в CSS.
После удаления такого класса в HTML не останется ненужных тегов.

```html
<article>
  <p>
    <span class="first-letter">Ж</span>ил старик со своею старухой <br>
    ...
  </p>
</article>
```
```css
article p::first-letter {
  color: #f44336;
  ...
}
```

## before и after

::before и ::after позволяют создать новый контент внутри HTML дерева. Этот контент привязан к определенному элементу и может появляться до него или после. Именно поэтому псевдоэлементы называются так:

- ::before — псевдоэлемент, позволяющий добавить контент перед выбранным элементом.
- ::after — псевдоэлемент, позволяющий добавить контент после выбранного элемента.

Каждый из этих псевдоэлементов должен включать специальное свойство content, внутри которого и указывается, что должно быть внутри. Без этого свойства псевдоэлементы ::before и ::after работать не будут.


## Переполнение
Переполнение  контента внутри блока — распространенное явление при верстке контента. Переполнением считается ситуация, при которой контент внутри контейнера больше, чем размер самого контейнера. Распространенный случай такого поведения — использование контейнера с фиксированными значениями высоты и ширины.

--

Интересно: использование фиксированных значений высоты и ширины в большинстве случаев не является хорошей практикой. Так можно достаточно быстро сверстать блок по макету, но одновременно с этим отнимается возможность расширения функционала. Любой отход от изначального контента может привести к проблемам, связанным с выходом контента из контейнера. Используйте фиксированные значения высоты и ширины там, где это предполагается в дизайне или для создания специфичной функциональности.

--

Для этого существует три свойства:

1) overflow-x — управление переполнением по горизонтали.
2) overflow-y — управление переполнением по вертикали.
3) overflow — сокращенная запись двух предыдущих свойств. Если указать внутри только одно значение, то оно применится к двум осям одновременно. Наиболее распространенный вариант использования.

```css
    overflow: hidden;

    overflow: scroll;
    
    overflow: auto;



```

## CSS Variables

Допускается использование и объявление переменных в коде стилей для 
переиспользования по коду в файле.

```css
:root {
  --main-background: #ccc;
}

.header {
  display: flex;
  width: 100%;
  height: 50px;

  font: 18px/1.5, sans-serif;

  background-color: var(--main-background);
}
```

Области видимости переменных:
В этом примере переменная --padding доступна только для блока с классом main-section и всех его потомков

```css
.main-section {
  --padding: 20px 30px;

  padding: var(--padding);
}
```

При использовании функции var() можно указать не только имя переменной, но и значение по умолчанию, если вдруг в переменной ничего нет. Ситуация не настолько частая, но знать про такую особенность важно.

```css
.section {
background: var(--bg, #fff);
}
```
Если переменной --bg нет, то, в качестве значения будет использовано значение #fff


## Фон

Свойство background является обобщенным для 8 свойств:

- background-attachment
- background-clip
- background-color
- background-image
- background-origin
- background-position
- background-repeat
- background-size

обобщенные свойства сбрасывают все предыдущие связанные свойства. Это важно, так как у вас уже могут быть установлены фоновые изображения, их позиционирование и размеры. Если добавить цвет с помощью свойства background в таком блоке, то прошлые свойства будут сброшены до значений по умолчанию.

Подробное описание см тут
https://ru.hexlet.io/courses/css-content/lessons/background/theory_unit 

## Градиенты

https://ru.hexlet.io/courses/css-content/lessons/gradient/theory_unit











