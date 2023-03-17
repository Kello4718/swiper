# Документация по swiper.js

## Подключение

> Все о подключении вы сможете найти на основной странице библиотеки [https://swiperjs.com/get-started](https://swiperjs.com/get-started), здесь же я расскажу о настройках библиотеки

## Настройки общие

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
direction | vertical или horizontal | Задает направление Swiper | Значение по умолчанию horizontal. Для корректной работы при vertical лучше задать высоту слайдера
loop | true или false | Бесконечная прокрутка | Значение по умолчанию true. Не будет работать если slidesPerColumn > 1
autoHeight | true или false | Автовысота | Если картинки разные по размеру, то при включенной данной настройке слайдер будет подстраиваться под каждый слайд. Если slidesPerView > 1, то слайдер будет подстраиваться под группу
slideToClickedSlide | true или false | Переключение слайда при клике на него | Значение по умолчанию false. Работает если клик происходит по следующему слайду.
slidesPerView | Любое число | Количество слайдов по умолчанию | Если поставить значение auto, то необходимо будет в стилях для слайда задать width: auto. Также auto не будет работать если slidesPerColumn > 1. Также можно указывать не целые числа, а например 2.5, 3.75. Также хочу отметить, что может быть такой случай, когда значение указано 3, а слайдов меньше чем 3, например 1. Тогда слайдер все равно будет работать, но смотриться это странно. В таком случае лучше добавить свойство watchOverflow, которое отключит слайдер, пока элементов не станет больше, чем указанное количество. `p.s. почему-то не работает сочетание с watchOverflow, надо разобраться`
slidesPerGroup | Любое число | Количество слайдов в группе при листании по умолчанию | Например пролистывать 3 слайда за раз
slidesPerColumn | Любое число | Мультирядность | Для корректной работы autoHeight: false, для всего слайдера в стилях нужно установить высоту, и изменить высоту слайда. Например если 2 ряда, то height: calc((100% - 30px) / 2), где 30px - расстояние между слайдами. `p.s. данное свойство почему-то не работает, надо разобраться`
spaceBetween | Любое число | Отступы между слайдами | Например 30, 100
watchOverflow | true или false | Отключение функционала, если слайдов меньше чем нужно | По умолчанию false. Связан с slidesPerView
centeredSlides | true или false | Активный слайд по центру | По умолчанию false
initialSlide | Любое число | Стартовый слайд | Первый слайд = 0
freeMode | true или false | Свободный режим | В свободном режиме мы можем листать слайды просто как ленту
speed | Любое число | Скорость переключения слайдов | По умолчанию 300. Чем больше тем плавнее переключаются слайды

## Настройки по параллаксу
Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
parallax | true или false | Задает эффект параллакса | Значение по умолчанию false.

> В html у элемента, которому мы хотим задать параллакс необходимо добавить дата-артибут data-swiper-parallax

> Пример реализации в html

```html
<div class="swiper-slide preview__swiper-slide">
  <img class="preview__swiper-slide-image" src="/img/screen-1/layer-background.jpg" alt="" data-swiper-parallax="30%">                     
</div>
```

## Настройки по перетаскиванию слайдов на ПК

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
simulateTouch | true или false | Перетаскивание слайда мышкой на ПК | Значение по умолчанию true
touchRatio | Любое число | Чувствительность для simulateTouch | Значение по умолчанию 1. Для того, чтобы на переключение слайда потребовалось меньше усилий это значение нужно увеличивать. Значение 0 отключит перетаскивание на всех устройствах
touchAngle | Любое число | Угол срабатывания перетаскивания | Например 45, 90
grabCursor | true или false | Изменить курсор мыши при перетаскивании на ПК | Значение по умолчанию false.

## Настройки по анимации

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
effect | 'slide', 'fade', 'flip', 'cube', 'coverflow' | Эффекты переключения слайдов | Работает нормально только с slidesPerView: 1

> Если effect : 'fade', то к нему открываются дополнительные настройки

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
crossFade | true или false | Параллельная смена прозрачности | ---

> Пример реализации

```js
 effect: 'fade',
 fadeEffect: {
    crossFade : false,
  },
```

> Если effect : 'flip', то к нему открываются дополнительные настройки

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
slideShadows | true или false | Тень | ---
limitRotation | true или false | Показ только активного слайда | ---

> Пример реализации

```js
 effect: 'flip',
 flipEffect: {
    slideShadows: true,
    limitRotation: true
  },
```

> Если effect : 'cube', то к нему открываются дополнительные настройки

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
slidesShadows | true или false | Тень в слайдах | ---
shadow | true или false | Тень в слайдах | ---
shadowOffset | Любое число | Настройки тени | Например 20, 40
shadowScale | Любое число | Масштабность тени | Например 0.01, 1.29

> Пример реализации

```js
 effect: 'cube',
 cubeEffect: {
  slidesShadows: true,
  shadow: true,
  shadowOffset: 30,
  shadowScale: 1,
 },
```

> Если effect : 'coverflow', то к нему открываются дополнительные настройки

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
rotate | Любое число | Угол | Например 10, 40
stretch | Любое число | Наложение | Например 10, 40
slideShadows | true или false | Тень | ---

> Пример реализации

```js
 effect: 'coverflow',
 coverflowEffect: {
  rotate: 20,
  stretch: 50,
  slideShadows: true,
 },
```

## Настройки по автопрокрутке

> Если мы хотим поуправлять настройками автопрокрутки, то для нас открываются следующие свойства

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
delay | Любое число | Пауза между прокруткой | По умолчанию 3000. Например 1000 (1 секунда)
stopOnLastSlide | true или false | Закончить на последнем слайде | Работает при loop: false
disableOnInteraction | true или false | Отключить после ручного переключения | Как только мы вмешаемся в его работу функционал прекратит работать если его значение равно true. Если нам нужно, чтобы он снова продолжил работать, то значение должно быть false

> Пример реализации

```js
autoplay: {
 delay: 1000,
 stopOnLastSlide: true,
 disableOnInteraction: true,
},
```
## Настройки по адаптивности

> Если мы хотим поуправлять настройками адаптивности, то необходимые нам свойства нужно вставить в определенную конструкцию. Стоит отметить, что мы можем управлять только теми свойствами, которые не влияют на логику. Например сменить логику прокрутки с горизонтальной на вертикальную мы не можем, а вот изменить количество слайдов при прокрутки мы можем

> Пример реализации

```js
  breakpoints: {
    320: {
      slidesPerView : 1,
    },

    1024: {
      slidesPerView : 2,
    },
  },
```

> Где 320 - это значит от 320 и больше

## Настройки по картинкам

> Для начала нам нужно изменить верстку слайда. Здесь мы добавляем специальный класс 'swiper-lazy' и добавляем data-атрибут data-src='путь к картинке'.

> Пример реализации разметки

```html
<div class="swiper-slide events-swiper__slide">
    <img class="events-swiper__slide-image swiper-lazy" data-src="/local/static/build/img/suggestion/events/slide-1.jpg" src="/local/static/build/img/suggestion/events/slide-1.jpg" alt="" title="">
    <div class="swiper-lazy-preloader"></div>
</div>
```

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
preloadImage | true или false | Отключить предзагрузку картинок | По умолчанию true - это значит, что картинки предзагружаются. Если мы хотим ускорить загрузку сайта, то лучше выключить

> Если мы хотим настроить подгрузку картинок, то нам открываются следующие свойства. Таким образом мы колоссально ускоряем загрузку нашего сайта.

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
loadOnTransitionStart | true или false | Подгружать на старте переключения слайда | Если значение true, то подгрузка начнется тогда, когда мы нажмем на след слайд, либо на предыдущий слайд
loadPrevNext | true или false | Подгружать предыдущую и следующую картинки | Если true, то сразу подгрузятся картинки из предыдущего и следующего слайда
watchSlidesProgress | true или false | Слежка за видимыми слайдами | Включать эти настройки, когда slidesPerView : auto или > 1
watchSlidesVisibility | true или false | Добавление класса видимым свойствам | Включать эти настройки, когда slidesPerView : auto или > 1

> Пример реализации

```js
  preloadImage: false,
  lazy: {
    loadOnTransitionStart: false,
    loadPrevNext: false,
  },
  watchSlidesProgress: true,
  watchSlidesVisibility: true,

```

## Настройки по обновлению слайдера

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
observer | true или false | Обновить слайдер при изменении его элементов | ---
observeParents | true или false | Обновить слайдер при изменении его родительских элементов | ---
observeSlideChildren | true или false | Обновить слайдер при изменении его дочерних элементов | ---

## Настройки навигации по хэшу

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
watchState | true или false | Отслеживать состояние | Каждому слайду нужно задать атрибут в HTML data-hash и прописать значение

> Пример реализации

```js
  hashNavigation: {
    watchState: true
  },
```

> В HTML необходимо добавить каждому слайду атрибут data-hash="любой текст". Пример реализации в HTML

```html
<div data-hash="black-dog" class="swiper-slide">
  <img src="black-dog.png" width="200" height="200">
</div>
```

> Теперь у нас в ссылке при клике на слайд будет добавляться хэш-тег к определенному слайду. Также мы можем переключать слайды теперь по навигационным стрелкам браузера

## Настройки по управлению с клавиатуры

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
enabled | true или false | Активировать управление с клавиатуры | По умолчанию false.
onlyInViewport | true или false | Управление только когда слайдер в пределах вьюпорта | По умолчанию true. Полезное свойство, которое предотвращает пролистывание слайдера вне видимой области
pageUpDown | true или false | Управление клавишами pageUp, padeDown | По умолчанию true.

> Пример реализации

```js
  keyboard: {
    enabled: true,
    onlyInViewport: true,
    pageUpDown: true,
  },
```

## Настройки по управлению слайдером через колесо мыши

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
sensitivity | Любое число | Чувствительность колеса мыши | Например 1, 2, 4
eventsTarget | Строка | Класс объекта, на котором будет срабатывать прокрутка мышью | Здесь нужно будет указать класс слайдера. Например '.swiper'. Если на странице есть 2 слайдера с таким классом, то пролистываться будут оба.

> Пример реализации

```js
  mousewheel: {
    sensitivity: 1,
    eventsTarget: '.swiper',
  },
```

## Настройки по пагинации

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
el | Строка | Класс для подключения блока с пагинацией | Например '.swiper-pagination'
clickable | true или false | Возможность листать слайды по нажатию на буллит | ---
dynamicBullets | true или false | Сделать булиты динамическими | Активный буллит больше
type | 'fraction', 'bullets', 'progressbar' | Вид буллитов | Активный буллит больше
renderBullet | function | Функция, которая сделает буллиты нумеруемыми | ---
renderFraction | function | Функция, которая сделает фракции нумеруемыми | ---

> Пример реализации функции, если type: 'bullets'

```js
    type: 'bullets',
    renderBullet: function (index, className) {
      return `<span class="${className}">${index + 1}</span>`;
    },
```

> Пример реализации функции, если type: 'fraction'

```js
    type: 'fraction',
    renderFraction: function (currentClass, totalClass) { 
      return `Фото <span class="${currentClass}"></span> из <span class="${totalClass}"></span>`;
    },
```

> Пример реализации

```js
   pagination: {
    el: '.swiper-pagination',
    clickable: true,
    dynamicBullets: true,

    type: 'bullets',
    renderBullet: function (index, className) {
      return `<span class="${className}">(${index} + 1)</span>`;
    },
  },
```

## Настройки по навигационным стрелкам

Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
nextEl | Строка | Класс для подключения кнопки стрелка влево | Например '.swiper-button-next'
prevEl | Строка | Класс для подключения кнопки стрелка право | Например '.swiper-button-prev'

> Пример реализации
 
```js
  navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },
```

## Настройки по скроллбару
Свойство | Возможное значение | Описание | Комментарий
--- | --- | --- | ---
el | Строка | Класс для подключения скроллбара | Например '.swiper-scrollbar'
draggable | true или false | Возможность перетаскивать слайды с помощью скролла | ---

> Пример реализации
 
```js
  scrollbar: {
    el: '.swiper-scrollbar',
    draggable: true,
  },
```
