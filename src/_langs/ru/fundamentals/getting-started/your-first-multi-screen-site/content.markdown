---
layout: article
title: "Работа с контентом и структурой сайта"
description: "Контент — это самый важный компонент любого интернет-ресурса. Из этого руководства вы узнаете, как создать свой первый сайт, который будет одинаково хорошо открываться на устройствах любого типа."
introduction: "Контент — это самый важный компонент любого интернет-ресурса. Именно контент определяет, каким должен быть дизайн сайта. В этом руководстве мы сперва определим, какие материалы будут представлены на сайте, затем опишем структуру страницы для этого контента и создадим страницу с простой линейной разметкой, которая одинаково хорошо выглядит как на узких, так и на широких экранах."
notes:
  styling:
    - О стиле мы напишем позже
article:
  written_on: 2014-04-17
  updated_on: 2014-04-23
  order: 1
id: multi-screen-content
collection: multi-screen
authors:
  - paulkinlan
translators:
related-guides:
  create-amazing-forms:
    -
      title: Как создавать удобные формы для ввода информации
      href: fundamentals/input/form/
      section:
        id: user-input
        title: "Формы"
        href: fundamentals/input/form/
    -
      title: Как определять элементы ввода
      href: fundamentals/input/form/label-and-name-inputs
      section:
        id: user-input
        title: "Формы"
        href: fundamentals/input/form/
    -
      title: Как выбрать нужный элемент ввода
      href: fundamentals/input/form/choose-the-best-input-type
      section:
        id: user-input
        title: "Формы"
        href: fundamentals/input/form/
  video:
    -
      title: Как эффективно работать с видеоматериалами
      href: fundamentals/media/video/
      section:
        id: introduction-to-media
        title: "Видео"
        href: fundamentals/media/
    -
      title: Как изменить время начала видеоролика
      href: fundamentals/media/video/add-a-video#specify-a-start-and-end-time
      section:
        id: introduction-to-media
        title: "Видео"
        href: fundamentals/media/
    -
      title: Как поставить картинку на заставку
      href: fundamentals/media/video/add-a-video#include-a-poster-image
      section:
        id: introduction-to-media
        title: "Видео"
        href: fundamentals/media/
  images:
    -
      title: Как эффективно работать с изображениями
      href: fundamentals/media/images/
      section:
        id: introduction-to-media
        title: "Изображения"
        href: fundamentals/media/
    -
      title:  Как правильно размещать изображения в разметке
      href: fundamentals/media/images/images-in-markup
      section:
        id: introduction-to-media
        title: "Изображения"
        href: fundamentals/media/
    -
      title: Как оптимизировать изображения
      href: fundamentals/performance/optimizing-content-efficiency/image-optimization
      section:
        id: introduction-to-media
        title: "Изображения"
        href: fundamentals/media/

key-takeaways:
  content-critical:
    - Определите, с какими материалами вы будете работать.
    - Продумайте информационную архитектуру сайта для областей просмотра разной ширины.
    - Создайте эскиз страницы с материалами, но пока не добавляйте на нее дизайн.
---

{% wrap content %}

{% include modules/toc.liquid %}

## Создание структуры страницы

Итак, нам необходимы:

1.  Область, в которой в общих чертах будет рассказываться о нашем продукте `С8256: курс по разработке мобильных сайтов`.
2.  Форма для сбора информации. С ее помощью мы сможем собирать данные о прользователях, заинтересовавшихся продуктом.
3.  Подробное описание и видеоролик.
4.  Изображения, показывающие продукт в работе.
5.  Таблица со статистическими данными. В нашем случае она нужна для того, чтобы показать, каково процентное соотношение пользователей различных устройств.

{% include modules/takeaway.liquid list=page.key-takeaways.content-critical %}

Мы уже разработали примерную информационную архитектуру сайта и разметку для устройств с разной шириной экрана.

<div class="demo clear" style="background-color: white;">
  <img class="g-wide--1 g-medium--half" src="images/narrowviewport.png" alt="Вариант для устройств с узким экраном">
  <img  class="g-wide--2 g-wide--last g-medium--half g--last" src="images/wideviewport.png" alt="Вариант для устройств с широким экраном">
</div>

Оба варианта легко преобразуются в разделы страницы, с которыми мы будем работать на протяжении всего проекта.

{% include_code _code/addstructure.html structure %}

## Добавление контента на страницу

Основа сайта готова. Мы знаем, какие разделы будут на сайте, что будет в них отображаться и как расположить их относительно друг друга. Теперь можно начать создание сайта.

{% include modules/remember.liquid title="Note" inline="true" list=page.notes.styling %}

### Создание заголовка и формы

Заголовок и поле для подписки на уведомления — важные элементы страницы. Пользователь должен сразу их видеть.

В заголовок поместим простой текст, описывающий суть курса:

{% include_code _code/addheadline.html headline %}

Также нам необходимо создать форму.
В ней будут следующие поля: имя пользователя, номер телефона и время суток, в которое удобнее всего звонить.

Все формы должны содержать плейсхолдеры и описания. Таким образом, пользователь легко будет ориентироваться в форме и понимать, что необходимо вписать в то или иное поле. Корректно составленное описание формы позволит программам для людей с ограниченными возможностями (например, экранному диктору) считать информацию и воспроизвести ее пользователю. Атрибут name помогает браузеру автоматически заполнять поля.

Чтобы пользователю было удобно вводить информацию на мобильном устройстве, опишем семантические типы элемента ввода. Например, когда необходимо ввести номер телефона, клавиатура переключится в режим набора номера.

{% include_code _code/addform.html form %}

{% include modules/related_guides.liquid inline=true list=page.related-guides.create-amazing-forms %}

### Создание раздела с видеоматериалами и информацией

Этот раздел имеет более сложную структуру:
в нем будет располагаться список функций наших продуктов и плейсхолдер для видеоролика о работе с ними.

{% include_code _code/addcontent.html section1 %}

Видео часто используют, чтобы рассказать о продукте или идее в более интерактивном стиле или показать его в действии.

Чтобы без труда встроить видеоролик на свой сайт, воспользуйтесь этими советами:

*  чтобы пользователю было удобно проигрывать видео, добавьте атрибут controls;
*  чтобы сразу было понятно, о чем видео, включите в него изображение для заставки;
*  добавьте несколько элементов <source> для видео в разных форматах;
*  для случаев, когда браузер не может проигрывать видео на странице, добавьте фолбэк-текст со ссылкой на скачивание видеоролика.

{% include_code _code/addvideo.html video html %}

{% include modules/related_guides.liquid inline=true list=page.related-guides.video %}

### Создание раздела `Изображения`

Сайты с изображениями выглядят интереснее, чем сайты, содержащие только текст. Существует два типа изображений:

*  Контент-изображения. Они являются частью контента на сайте и пополняют информативную функцию.
*  Стилистические изображения. Их обычно помещают на фон страницы. Они делают внешний вид сайта более приятным. Подробнее об этом читайте в [следующей статье]({{site.baseurl}}{{page.article.next.url}}).

Раздел `Изображения` на нашем сайте будет содержать подборку контент-изображений.

Такие картинки крайне важны для передачи информации. Например, невозможно представить себе газеты и журналы без фотографий и рисунков. В этом курсе мы используем фотографии преподавателей Криса Уилсона, Питера Лубберса и Шона Беннета.

{% include_code _code/addimages.html images html %}

Эти изображения расположены так, чтобы заполнить экран по широкой стороне. Такую верстку удобнее всего использовать для устройств с узким экраном. На мониторах стационарных компьютеров она выглядит хуже. Подробнее о том, как сделать верстку удобной для разных экранов, мы поговорим в разделе `Отзвычивый дизайн`.

{% include modules/related_guides.liquid inline=true list=page.related-guides.images %}

У слабовидящих и незрячих людей нет возможности читать информацию на экране, поэтому они используют экранный диктор, который начитывает контент. Важно, чтобы все контент-изображения на странице имели содержательный тег alt. С его помощью экранный диктор сможет `прочесть` описание изображения.

Убедитесь, что текст максимально емко и кратко описывает картинку. В нашем примере для атрибута используется формат `Имя: должность`. Таким образом, пользователь поймет, что на этой странице рассказывается про авторов курса и их профессии.

### Добавление раздела с таблицей

Последний раздел содержит таблицу со статистическими данными о продукте.

Используйте таблицы только для предоставления табличных данных (например, для информационных матриц).

{% include_code _code/addcontent.html section3 %}

### Добавление `подвала страницы`

Чтобы внизу страницы всегда отображались ссылки на такие разделы, как `Условия использования`, в большинство сайтов необходимо встраивать `подвал` (footer).

На нашем сайте такими разделами будут `Контакты`, `Условия использования` и `Социальные сети`.

{% include_code _code/addcontent.html footer %}

## Заключение

Мы успешно создали макет сайта и обозначили его основные элементы. Также мы убедились, что контент сайта располагается в нужных разделах.

<div class="clear">
  <img class="g-wide--2 g-medium--half" src="images/content.png" alt="Content" style="max-width: 100%;">
  <img  class="g-wide--2 g-wide--last g-medium--half g--last" src="images/narrowsite.png" alt="" style="max-width: 100%;">
</div>

Наверное, вы уже заметили, что сейчас страница выглядит некрасиво. Мы намеренно оставили ее в таком виде. 
Контент — это неотъемлемая часть любого сайта. Поэтому сперва мы создаем условия для удобного отображения информации, а затем приступаем к оформлению внешнего вида сайта. Теперь у нашего сайта есть надежная структура. А о стиле мы поговорим в следующем разделе.

{% include modules/nextarticle.liquid %}

{% endwrap %}

