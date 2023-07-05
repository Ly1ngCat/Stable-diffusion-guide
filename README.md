![image](https://github.com/Ly1ngCat/Stable-diffusion-guide/assets/51241945/b87effea-fd93-40ea-af57-d413cad55d6c)# Stable-diffusion-guide
Руководство для новых пользователей Stable diffusion

# Начало работы

Stable diffusion - нейросеть, созданная для генерации изображений по текстовым описаниям и не только. Её преимуществом перед аналогами, такими как Midjourney или DALL-E, является её гибкость в настройке и обучении. Открытый исходный код позволяет развернуть данную нейросеть даже на домашнем ПК, а большое количество пользователей создают и выкладывают в общий доступ свои модификации, существенно расширяя имеющийся функционал. Например онлайн редактор положения тела персонажа. Но обо всём по порядку.

## Интерфейс

### Верхние блоки

Первое что мы видим открывая ссылку и вводя логин с паролем - это данное окно с множеством вкладок. Не пугайтесь, на деле всё проще чем выглядит, сейчас мы разберём какая вкладка и ползунок за что отвечает.
<img src="Screenshotes Stable diffusion/Снимок экрана 2023-06-19 083047.png" alt="альтернативный текст">

И так, мы пойдем по порядку фактическому, а не логическому и я просто расскажу про каждый блок сверху вниз.

<img src="Screenshotes Stable diffusion/Верхняя панель.png">
<img src="Screenshotes Stable diffusion/Верхняя панель2.png">

1. Выпадающий список с выбором моделей. Модель - это основной файл настроек нейросети, именно модель и отвечает за распознавание и генерацию изображений. Из-за разного обучения модели по разному могут понимать, видеть и изображать одни и те же объекты. Например, одна модель может попросту не знать что такое чайник, зато прекрасно работать с людьми, верно отображая анатомию и пропорции. Из наших моделей на данный момент я могу порекомендовать **_deliberate_v2_(Хороша под большинство запросов и различные стили), _revAnimated_v122_(Отлично работает с арт стилистикой, художниками и мультяшностью) и _reliberate_v10_(Создавалась специально под реализм)** С другими моделями можно ознакомиться на ресурсе https://civitai.com/

2. Данный блок отвечает за то, в какой рабочей области мы сейчас находимся. **txt2img** в расшифровке text to image, отвечает, как очевидно из названия, за генерацию картинки по текстовому описанию. **img2img** - за генерацию изображения из другого изображения. На самом деле, при генерации в **img2img**, мы так же можем использовать текст, но об этом чуть позже. Вкладка **Extras** отвечает за увеличение размеров изображения, но её функционал так же дублируется на экране img2img и я ни разу не нажимал именно на эту вкладку. Остальные блоки нам пока не понадобятся.

3. **Окно промта. Промт - текстовое описание, по которому нейросеть генерирует изображение.** Сочетая между собой различные промты и экспериментируя, можно добиться желаемого результата практически на любой модели. Умение писать промты очень сильно упростит работу с нейросетью. Рекомендую посмотреть https://www.youtube.com/watch?v=XqNStvV9Pg0&t=9s

4. **Окно негативного промта** - это то, что нейросеть не будет изображать. Например мы хотим сгенерировать реалистичного кота, в окне промта мы пишем realistic cat и всё равно кот получается как будто в 3д, мы можем добавить в негативный промт 3d, 3dcg, game, теперь наша нейросеть будет избегать 3д, что сделает нашего кота реалистичнее. О написании промтов и наиболее распространенных вариантах я расскажу ниже, пока мы говорим только про интерфейс.

5. Стили. Здесь всё очень просто, мы просто сохраняем всё что на данный момент написано в окне промт и окне негативный промт. При выборе стиля, всё что было написано, просто добавляется в свои окна. Давайте рассмотрим ситуацию из пункта выше. Сценарий с тем что нам будут необходимы реалистичные изображения будет часто повторяться. Мы можем в окне промта написать realistic, а в окне негативного промта 3d, 3dcg, game, и сохранить этот стиль с названием например Realistic. В следующий раз когда нам будет нужен реалистичный объект, мы можем просто написать что нам необходимо и выбрать нужный нам стиль Realistic.

6. Значение кнопок по порядку слева направо **Подтягивает настройки последней генерации**, **Очистить окна промт и негатив промт**, **Показать/скрыть дополнительные сети**, при выбраном стиле **Перенос всех промтов и негатив промтов в окна 3 и 4 из выбранного стиля** **Сохранить стиль**

7. Начать генерацию. Неочевидный момент, если мы нажмем правой кнопкой мыши, мы можем запустить и остановить бесконечную генерацию.

### Нижние блоки

<img src="Screenshotes Stable diffusion/Нижняя панель.png">

**Sampling method или же Сэмплер** - один из важнейших атрибутов после модели. Это алгоритм создания изображения после обработки текста моделью. Влияет на стиль исполнения понятого нейросетью текста и на скорость работы. Лучше самостоятельно поэкспериментировать с сэмлерами, поскольку никогда не знаешь заранее какой результат ты можешь получить.
На моём опыте я могу выделить такие сэмплеры:
**Euler A, DPM++ M2 Karras, DPM++ SDE Karras, Heun**

<img src="Screenshotes Stable diffusion/Сравнение сэмлеров.png">

**Sampling steps** - сколько раз Сэмплер пройдёт по тексту и картинке. Чем больше шагов, тем больше деталей, однако это палка о двух концах. Чем больше шагов, тем больше вероятность ненужных деталей - лишних пальцев, хвостов, глаз, ушей. Оптимально от 18 до 50 шагов.

**Restore faces** - восстановление лиц, работает плохо, лучше исправлять лица промтом или в inpaint.

**Hires. fix** - увеличение размеров изображения. Увеличивает время генерации.

**Tiling** - создание бесшовного изображения. Нужен дизайнерам для создания игровых текстур. Изображение продолжает само себя бесконечно и без разрывов и швов.

Пример тайлинга:

<img src="Screenshotes Stable diffusion/Бесшовная текстура.png">

Снова вернёмся к нижним блокам.

<img src="Screenshotes Stable diffusion/Нижняя панель2.png">

**Width, Height** - высота и ширина изображения в пикселях. Рекомендую ставить 640x640 или 768x760.

**Batch count**  - сколько изображений мы сделаем в строке.
**Batch size** - сколько будет строк.

**Seed** - стартовая точка, откуда нейросеть начнет свою работу. Простыми словами, указывая сид с тем же самым описанием, мы получим тот же самый результат. Однако, если мы поменяем даже одно слово в промте, результат будет отличаться. Параметр **-1** будет создавать случайное изображени.

**Script** - дополнительны скрипты. Изображение с художниками выше сделано как-раз с помощью скрипта X\Y\Z plot. О них я расскажу отдельно.

## Практика

Мы коротко прошлись по интерфейсу, теперь можно попробовать что-то сгенерировать.
Я например попробую сделать новогоднюю елку. Потому что лето, потому что логика!
Для начала попробуйте повторить за мной, сделать что-то своё вы успеете чуть позже, пока главное понять принцип и не теряться в интерфейсе.

Я просто напишу в промт **Christmas tree**.
Никакие настройки я сейчас трогать не буду, по умолчанию они уже неплохие и для первых нескольких дней в приложении мы можем использовать их. Главное убедитесь что у вас установлена та же модель что и у меня - **Deliberate_v2**

<img src="Screenshotes Stable diffusion/Модель.png">  
<br/>
<br/>
Нажимаем Generate

<img src="Screenshotes Stable diffusion/ёлка с подарками.png">

Но мне не навится слишком американский стиль, попробуем убрать подарки и напишем в Negative promt слово **Gifts**.

<img src="Screenshotes Stable diffusion/ёлка без подарков.png">

Получилось, мы убрали подарки. Можете попробовать самостоятельно убрать или добавить что-то. Попробуйте например убрать подарочные носки и камин. **Совет:** поставьте число **Batch count** например на 3. Это увеличит количество генерируемых картинок. Так проще понимать насколько нейросеть попадает в необходимый результат.

<img src="Screenshotes Stable diffusion/количество.png">

Можете поэкспериментировать, добавляйте, убирайте, одним словом практикуйтесь. Можете попробовать поменять модель. Если результат выглядит нереалистично, не пугайтесь, ведь вы не просили об этом нейросеть, чем больше вы ей опишите желаемый результат, тем больше вероятность что она его сделает. Например дописав пару промтов можно сделать ёлку немного приятнее глазу. Но об этом ниже, когда мы будем разбирать сами промты.

<img src="Screenshotes Stable diffusion/ёлка реалистичная.png">


## Подробнее про промты

Немного подробнее коснемся промтов, так как это основной инструмент взаимодействия с нейросетью. У промтов есть основные правила написания:
1. Порядок слов важен. Первое слово будет значить для нейросети больше, чем последнее.
2. Строки не важны. Лично я для удобства разделяю промты по логике. Например, на первой строке пишу и описываю сам объект. Кто или что, в какой позе, в какой одежде, что делает. На второй строке я описываю положение кадра, на третьей окружение, дополнительные объекты и тд.
3. Нейросеть отлично знает знаменитостей, актёров и художников. Это можно использовать в свою пользу при написании промтов. Чтобы использовать стиль какого-либо художника, использовать такой промт - by artist Greg Rutkowski, или же art by Greg Rutkowski. На просторах интернета нашел данную подборку художников. Низкий поклон автору https://github.com/Ly1ngCat/Stable-diffusion-guide/blob/main/Screenshotes%20Stable%20diffusion/artist_stable_diffusion_compressed.pdf

Так же у промтов в Stable Diffusion есть свой **синтаксис**.

### Синтаксис

Помимо самих значений слов, как негативных так и позитивных, мы можем настраивать наши промты еще немного глубже, управляя их весом. Для этого используются 3 вида скобок **(), [] и {}.**

**()** - увеличение веса промта. Например, написав (colored hair) без каких-либо коэффициентов, вы усилите эффект "цветных волос" в 1.1 раза. Если добавить больше скобок, сила воздействия дополнительно увеличится. Поэтому запись (((colored hair))) с значительной вероятностью поможет изменить цвет волос персонажа.

**(:1.1)** - альтернативный вариант записи как увеличения веса, так и уменьшения. Значение промта по умолчанию **1**, подобной записью мы увеличиваем или уменьшаем его вес **(colored hair:1.2)** или **(colored hair:0.5)**.

**[]** - Квадратные скобки — [] — полная противоположность круглым. Они используются для ослабления воздействия ключевых слов или удаления нежелательных объектов, появляющихся во время генерации изображений. Добавив [fern], вы уменьшите вероятность появления папоротника на картинке в 0.9 раз. Добавив больше квадратных скобок, можно полностью избавиться от папоротника.

**{}** - В данных фигурных скобках выбор делается между словами случайно. {colored hair | white hair}. Используется в основном чтобы добавить разнообразия изображению.
