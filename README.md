const swiper = new Swiper('.swiper', {
  // Настройки Swiper
  direction: 'vertical', // Направление Swiper. Варианты : vertical | horizontal
  loop: true, // Бесконечная прокрутка. (p.s. не будет работать если slidesPerColumn > 1). Варианты : true | false
  simulateTouch: true, // Перетаскивание слайда мышкой. Варианты : true | false
  touchRatio: 1, // Чувствительность simulateTouch. Варианты : 0 | 1 | 2 | ...
  touchAngle: 45, // Угол срабатывания перетаскивания. Варианты : 45 | 90 | ...
  grapCursor: true, // Изменить курсор мыши. Варианты : true | false
  slideToClickedSlide: true, // Переключение слайда при клике на него. Варианты : true | false
  autoHeight: true, // Автовысота. Варианты : true | false
  slidesPerView: 1, // Количество слайдов по умолчанию (p.s. если auto, то в стилях к слайду задать width: auto; и auto не будет работать если slidesPerColumn > 1). Варианты : auto | 1 | 2,5 | ...
  slidesPerGroup: 1, // Количество слайдов в группе при листании по умолчанию. Варианты : 1 | 2 | 2,5 | ...
  watchOverflow: true, // Отключение функционала, если слайдов меньше чем нужно (p.s. связан с slidesPerView). Варианты : true | false
  spaceBetween: 30, // Отступы между слайдами. Варианты : 30 | 50 | ...
  centeredSlides: true, // Активный слайд по центру (p.s. свойство не работает если slidesPerGroup: 1). Варианты : true | false
  initialSlide: 1, // Стартовый слайд (p.s. первый слайд = 0). Варианты : 0 | 1 | ...
  slidesPerColumn: 2, // Мультирядность (p.s. для корректной работы autoHeight: false, для всего слайдера в стилях нужно установить высоту, и изменить высоту слайда. Например если 2 ряда, то height: calc((100% - 30px) / 2), где 30px - расстояние между слайдами. Варианты : 1 | 2 | ...
  freeMode: true, // Свободный режим (p.s. в свободном режиме мы можем листать слайды просто как ленту). Варианты : true | false
  speed: 300, // Скорость переключения слайдов. Варианты : 300 | 400 | ...

  /* Анимации */

  effect: 'slide', // Эффекты переключения слайдов. Варианты : 'slide' | 'fade' | 'flip' | 'cube' | 'coverflow'
  // Дополнитело к эффекту 'fade'
  fadeEffect: {
    crossFade: true, // Параллельная смена прозрачности. Варианты : true | false
  },
  // Дополнительно к эффекту 'flip'
  flipEffect: {
    slideShadows: true, // Тень. Варианты : true | false
    limitRotation: true, // Показ только активного слайда. Варианты : true | false
  },
  // Дополнительно к эффекту 'cube'
  cubeEffect: {
    slidesShadows: true, // Тень в слайдах. Варианты : true | false
    shadow: true, // Тень в слайдах. Варианты : true | false
    shadowOffset: 20, // Настройки тени. Варианты : 20 | 40 | ...
    shadowScale: 0.94, // Масштабность тени. Варианты : 0.01 | 1.29 | ...
  },
  // Дополнительно к эффекту 'coverflow'
  coverflowEffect: {
    rotate: 20, // Угол. Варианты : 10 | 40 | ...
    stretch: 50, // Наложение. Варианты : 50 | 100 | ...
    slideShadows: true, // Тень. Варианты : true | false
  },

  /* конец настроек по анимациям*/

  // Автопрокрутка
  autoplay: {
    delay: 1000, // Пауза между прокруткой. Варианты : 1000 | 2000 | ...
    stopOnLastSlide: true, // Закончить на последнем слайде (p.s. при loop: false ). Варианты : true | false
    disableOnInteraction: true, // Отключить после ручного переключения. Варианты : true | false
  },
  // Адаптивность, например от 320, от 768 и так далее
  breakpoints: {
    320: {

    },

  },

  /* Настройки для картинок */

  preloadImage: false, // Отключить предзагрузку картинок (p.s. по умолчанию true - что значит, что картинки предзагружаются). Варианты : true | false

  // Подгрузка картинок

  lazy: {
    loadOnTransitionStart: false, // Подгружать на старте переключения слайда (p.s. подгрузка картинки начнется тогда, когда мы нажмем на след слайд). Варианты: true | false
    loadPrevNext: false, // Подгружать предыдущую и следующую картинки (p.s. если true, то сразу подгрузятся картинки из пред. и след. слайда). Варианты : true | false
  },

  watchSlidesProgress: true, // Слежка за видимыми слайдами (p.s. включать эти настройки, когда slidesPerView : auto | > 1). Варианты : true | false
  watchSlidesVisibility: true, // Добавление класса видимым свойствам (p.s. включать эти настройки, когда slidesPerView : auto | > 1). Варианты : true | false

  /* конец настроек для картинок */

  /* Обновление слайдера */

  observer: true, // Обновить свайпер при изменении элементов слайдера. Варианты : true | false
  observeParents: true, // Обновить свайпер при изменении родительских элементов слайдера. Варианты : true | false
  observeSlideChildren: true, // Обновить свайпер при изменении дочерних элементов слайдера. Варианты : true | false

  /* конец настроек для обновления слайдера */

  // Навигация по хэшу
  hashNavigation: {
    watchState: true, // Отслеживать состояние (p.s каждому слайду нужно задать атрибут в HTML data-hash и прописать значение). Варианты : true | false
  },

  //Управление с клавиатуры
  keyboard: {
    enabled: true, // Активировать управление с клавиатуры. Варианты : true | false
    onlyInViewport: true, // Управление только когда слайдер в пределах вьюпорта. Варианты : true | false
    pageUpDown: true, // Управление клавишами pageUp, padeDown. Варианты : true | false
  },

  // Управление слайдером через колесо мыши
  mousewheel: {
    sensitivity: 1, // Чувствительность колеса мыши. Варианты : 1 | 2 | ...
    eventsTarget: '.swiper', // Класс объекта, на котором будет срабатывать прокрутка мышью
  },

  // Пагинация
  pagination: {
    el: '.swiper-pagination', // Класс для подключения блока с пагинацией
    clickable: true, // Можно ли листать слайды по нажатию на буллит. Варианты : true | false
    dynamicBullets: true, // Сделать булиты динамическими. (p.s. активный буллит больше). Варианты : true | false

    type: 'bullets', // Вид буллитов. Варианты: fraction | bullets | progressbar
    renderBullet: function (index, className) { // Функция, которая сделает буллиты нумеруемыми (под буллиты)
      return `<span class="${className}">(${index} + 1)</span>`;
    },
    renderFraction: function (currentClass, totalClass) { // Функция, которая видоизменяет буллиты (под фракции)
      return `Фото <span class="${currentClass}"></span> из <span class="${totalClass}"></span>`;
    },

  },

  // Навигационные стрелки
  navigation: {
    nextEl: '.swiper-button-next', // Класс для подключения кнопки стрелка влево
    prevEl: '.swiper-button-prev', // Класс для подключения кнопки стрелка право
  },

  // Скроллбар
  scrollbar: {
    el: '.swiper-scrollbar', // Класс для подключения скроллбара
    draggable: true, // Возможность перетаскивать слайды с помощью скролла. Варианты : true | false
  },
});

