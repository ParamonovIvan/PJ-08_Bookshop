# Проект «Книжный интернет-магазин на API Google Books»

### Задача проекта:

+ Сверстать главную страницу интернет-магазина Bookshop.

+ Подключить Google Books API так, чтобы данные о книгах подгружались с сервера.

+ Подключить созданный ранее слайдер.

+ Поработать над правильной организацией проекта.

  &nbsp;&nbsp;&nbsp; реализовать модульную структуру;

  &nbsp;&nbsp;&nbsp; подключить Webpack;

  &nbsp;&nbsp;&nbsp; настроить сборку с минификацией.

+ Применить пройденные ранее инструменты оптимизации.

### Функциональные требования:

+ Шапка сайта.

Шапка содержит логотип, навигацию и набор кнопок. Ссылки в меню можно оставить пустыми, так как реализация остальных страниц сайта в проекте не предусмотрена.

Кнопки авторизации, поиска и корзины неактивны. Однако при добавлении товара в корзину у иконки должен появиться бейджик с количеством товара в корзине.

При прокрутке сайта шапка должна оставаться закреплённой в верхней части экрана.

+ Слайдер.

Под шапкой сайта располагается слайдер.

Слайдер автоматически пролистывает изображения каждые 5 секунд, а после последнего изображения вновь переключается на первое. Перелистывать изображения можно также с помощью точек под слайдером.

Справа от слайдера располагаются цветные блоки. Их нужно сверстать как ссылки, адреса ссылок можно оставить пустыми.

+ Список категорий и список книг.

Под слайдером в левой части экрана располагается список категорий. Активная категория должна быть выделена визуально.

По умолчанию в качестве активной выбрана первая категория в списке. Клик на неактивную категорию делает её активной, и список книг перезагружается, чтобы отобразить книги из этой категории.

Список книг подгружается из Google Books API в соответствии с выбранной категорией. Для списка книг необходимо реализовать ленивую загрузку: сначала подгружаются первые 6 книг, по клику на кнопку «Load more» — ещё 6, и так далее.

+ Карточка книги.

В карточке книги должна быть отображена следующая информация:

  &nbsp;&nbsp;&nbsp; Обложка. Если API не возвращает обложку, подставить вместо неё любую картинку-плейсхолдер.

  &nbsp;&nbsp;&nbsp; Автор. Если авторов несколько, перечислить их через запятую.

  &nbsp;&nbsp;&nbsp; Заголовок.

  &nbsp;&nbsp;&nbsp; Рейтинг: от 1 до 5 звёздочек плюс общее количество отзывов. Если в данных о книге нет рейтинга, не показывать эту строчку.

  &nbsp;&nbsp;&nbsp; Описание. Если текст в описании занимает больше 3-х строк, его нужно обрезать и добавить в конце многоточие.

  &nbsp;&nbsp;&nbsp; Цена с указанием валюты. Если в данных о книге нет цены, не показывать эту строчку.

Под описанием каждой книги должна быть кнопка «Buy now». При клике на неё товар добавляется в корзину, а кнопка меняет внешний вид. При повторном нажатии на кнопку товар убирается из корзины.

Информация о книгах, добавленных в корзину, должна сохраняться в localStorage.

### Технические требования:

+ Книжный магазин должен быть реализован по принципу SPA.
То есть все действия пользователя: подгрузка книг, переключение категории — происходят без перезагрузки страницы.

+ JS-файлы в проекте должны быть разделены на модули (ES6), структура файлов должна быть логичной и понятной.

+ Для создания проекта необходимо использовать npm. В папке проекта должны быть файлы package.json и package-lock.json. В package.json необходимо прописать скрипт npm run build, который будет запускать сборку проекта.

+ К проекту необходимо подключить Webpack.

Если запустить сборку проекта, ожидается следующий результат:

  &nbsp;&nbsp;&nbsp; Сборка завершается успешно и без ошибок;

  &nbsp;&nbsp;&nbsp; CSS-файлы также является частью сборки;

  &nbsp;&nbsp;&nbsp; CSS подключается отдельным файлом, не в теге ``` <style> ```;

  &nbsp;&nbsp;&nbsp; JS и CSS-файлы минифицируются в процессе сборки.

+ В проекте необходимо использовать ещё как минимум 2 инструмента оптимизации разработки (помимо npm и Webpack). Можно выбрать любые из списка:

  &nbsp;&nbsp;&nbsp; Методология БЭМ;

  &nbsp;&nbsp;&nbsp; CSS-препроцессор Sass (или аналог);

  &nbsp;&nbsp;&nbsp; Шаблонизатор pug или аналог;

  &nbsp;&nbsp;&nbsp; Webpack Dev Server;

  &nbsp;&nbsp;&nbsp; Линтер.

### Требования к верстке и CSS:

+ Вёрстка должна соответствовать макету. Добиваться Pixel-Perfect соответствия не обязательно, но основные моменты должны быть соблюдены:

  &nbsp;&nbsp;&nbsp; Цветовая гамма,

  &nbsp;&nbsp;&nbsp; Шрифты,

  &nbsp;&nbsp;&nbsp; Размеры,

  &nbsp;&nbsp;&nbsp; Отступы.

+ Приложение должно корректно отображаться на различных разрешениях. Дизайна для мобильной версии в макете нет, поэтому нужно реализовать её самостоятельно.

+ Необходимо соблюдать семантическую вёрстку.

В приложении должны присутствовать разделы ``` <header> ```, ``` <main> ``` и ``` <nav> ```. Ссылки должны быть прописаны в теге ``` <a> ```, кнопки должны быть реализованы элементом ``` <button> ```, и так далее. Не забывать также про обязательный атрибут alt у изображений.

+ При наведении курсора на любые кликабельные элементы должен появляться cursor: pointer.

+ Использовать селекторы по тегу и id для задания стилей нельзя. Использовать классы.

### Прочие требования:

+ Писать код аккуратно, с соблюдением форматирования и отступов.

+ Стараться давать CSS-классам, переменным и функциям осмысленные имена.

+ Стараться использовать современный ES6 синтаксис: стрелочные функции, декомпозицию, Spred и т.д.

+ При написании кода стараться следовать принципам KISS (Keep It Short and Simple - не усложняй) и DRY (Don’t Repeat Yourself - не повторяйся).

### Иснтрукция для разработки и тестирования

+ npm

```
npm i
npm run build
npm run start
```
+ yarn

```
yarn
yarn run start
```

### Результат работы:
#### Страница книжного интернет-магазин на API Google Books

![bookshop](https://github.com/ParamonovIvan/Bookshop_PJ-08/assets/131868856/5047d076-f0a3-4794-918d-79ffdc1d5045)
