<h1>Книжный интернет-магазин на API Google Books</h1>

<h3>Задача проекта:</h3>
• Сверстать главную страницу интернет-магазина Bookshop.<br>
• Подключить Google Books API так, чтобы данные о книгах подгружались с сервера.<br>
• Подключить созданный ранее слайдер.<br>
• Поработать над правильной организацией проекта:<br>
  &nbsp;&nbsp;&nbsp; реализовать модульную структуру;<br>
  &nbsp;&nbsp;&nbsp; подключить Webpack;<br>
  &nbsp;&nbsp;&nbsp; настроить сборку с минификацией.<br>
• Применить пройденные ранее инструменты оптимизации.<br>

<h3>Функциональные требования:</h3>
• Шапка сайта.<br>
Шапка содержит логотип, навигацию и набор кнопок. Ссылки в меню можно оставить пустыми, так как реализация остальных страниц сайта в проекте не предусмотрена.<br>
Кнопки авторизации, поиска и корзины неактивны. Однако при добавлении товара в корзину у иконки должен появиться бейджик с количеством товара в корзине.<br>
При прокрутке сайта шапка должна оставаться закреплённой в верхней части экрана.<br>
• Слайдер.<br>
Под шапкой сайта располагается слайдер.<br>
Слайдер автоматически пролистывает изображения каждые 5 секунд, а после последнего изображения вновь переключается на первое. Перелистывать изображения можно также с помощью точек под слайдером.<br>
Справа от слайдера располагаются цветные блоки. Их нужно сверстать как ссылки, адреса ссылок можно оставить пустыми.<br>
• Список категорий и список книг.<br>
Под слайдером в левой части экрана располагается список категорий. Активная категория должна быть выделена визуально.<br>
По умолчанию в качестве активной выбрана первая категория в списке. Клик на неактивную категорию делает её активной, и список книг перезагружается, чтобы отобразить книги из этой категории.<br>
Список книг подгружается из Google Books API в соответствии с выбранной категорией. Для списка книг необходимо реализовать ленивую загрузку: сначала подгружаются первые 6 книг, по клику на кнопку «Load more» — ещё 6, и так далее.<br>
• Карточка книги.<br>
В карточке книги должна быть отображена следующая информация:<br>
  &nbsp;&nbsp;&nbsp; Обложка. Если API не возвращает обложку, подставить вместо неё любую картинку-плейсхолдер.<br>
  &nbsp;&nbsp;&nbsp; Автор. Если авторов несколько, перечислить их через запятую.<br>
  &nbsp;&nbsp;&nbsp; Заголовок.<br>
  &nbsp;&nbsp;&nbsp; Рейтинг: от 1 до 5 звёздочек плюс общее количество отзывов. Если в данных о книге нет рейтинга, не показывать эту строчку.<br>
  &nbsp;&nbsp;&nbsp; Описание. Если текст в описании занимает больше 3-х строк, его нужно обрезать и добавить в конце многоточие.<br>
  &nbsp;&nbsp;&nbsp; Цена с указанием валюты. Если в данных о книге нет цены, не показывать эту строчку.<br>
Под описанием каждой книги должна быть кнопка «Buy now». При клике на неё товар добавляется в корзину, а кнопка меняет внешний вид. При повторном нажатии на кнопку товар убирается из корзины.<br>
Информация о книгах, добавленных в корзину, должна сохраняться в localStorage.<br>

<h3>Технические требования:</h3>
• Книжный магазин должен быть реализован по принципу SPA.<br>
То есть все действия пользователя: подгрузка книг, переключение категории — происходят без перезагрузки страницы.<br>
• JS-файлы в проекте должны быть разделены на модули (ES6), структура файлов должна быть логичной и понятной.<br>
• Для создания проекта необходимо использовать npm. В папке проекта должны быть файлы package.json и package-lock.json. В package.json необходимо прописать скрипт npm run build, который будет запускать сборку проекта.<br>
• К проекту необходимо подключить Webpack.<br>
Если запустить сборку проекта, ожидается следующий результат:<br>
  &nbsp;&nbsp;&nbsp; Сборка завершается успешно и без ошибок;<br>
  &nbsp;&nbsp;&nbsp; CSS-файлы также является частью сборки;<br>
  &nbsp;&nbsp;&nbsp; CSS подключается отдельным файлом, не в теге <style>;<br>
  &nbsp;&nbsp;&nbsp; JS и CSS-файлы минифицируются в процессе сборки.<br>
• В проекте необходимо использовать ещё как минимум 2 инструмента оптимизации разработки (помимо npm и Webpack). Можно выбрать любые из списка:<br>
  &nbsp;&nbsp;&nbsp; Методология БЭМ;<br>
  &nbsp;&nbsp;&nbsp; CSS-препроцессор Sass (или аналог);<br>
  &nbsp;&nbsp;&nbsp; Шаблонизатор pug или аналог;<br>
  &nbsp;&nbsp;&nbsp; Webpack Dev Server;<br>
  &nbsp;&nbsp;&nbsp; Линтер.<br>

<h3>Требования к верстке и CSS:</h3>
• Вёрстка должна соответствовать макету. Добиваться Pixel-Perfect соответствия не обязательно, но основные моменты должны быть соблюдены:<br>
  &nbsp;&nbsp;&nbsp; Цветовая гамма,<br>
  &nbsp;&nbsp;&nbsp; Шрифты,<br>
  &nbsp;&nbsp;&nbsp; Размеры,<br>
  &nbsp;&nbsp;&nbsp; Отступы.<br>
• Приложение должно корректно отображаться на различных разрешениях. Дизайна для мобильной версии в макете нет, поэтому нужно реализовать её самостоятельно.<br>
• Необходимо соблюдать семантическую вёрстку.<br>
В приложении должны присутствовать разделы ```<header>```, ```<main>``` и ```<nav>```. Ссылки должны быть прописаны в теге ```<a>```, кнопки должны быть реализованы элементом ```<button>```, и так далее. Не забывать также про обязательный атрибут alt у изображений.<br>
• При наведении курсора на любые кликабельные элементы должен появляться cursor: pointer.<br>
• Использовать селекторы по тегу и id для задания стилей нельзя. Использовать классы.<br>

<h3>Прочие требования:</h3>
• Писать код аккуратно, с соблюдением форматирования и отступов.<br>
• Стараться давать CSS-классам, переменным и функциям осмысленные имена.<br>
• Стараться использовать современный ES6 синтаксис: стрелочные функции, декомпозицию, Spred и т.д.<br>
• При написании кода стараться следовать принципам KISS (Keep It Short and Simple - не усложняй) и DRY (Don’t Repeat Yourself - не повторяйся).<br>

<h3>Результат работы:<h3><h4>Страница книжного интернет-магазин на API Google Books</h4>

![bookshop](https://github.com/ParamonovIvan/Bookshop_PJ-08/assets/131868856/5047d076-f0a3-4794-918d-79ffdc1d5045)
