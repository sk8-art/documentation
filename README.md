

# Содержание <a id="content"></a>
---
1. [CSS](#css)
   
    1.1 [Подчеркивание](#underline)
2. [Методология БЭМ](#met)
3. [Git](#git)

   3.1 [Основы](#bases)
   
4. [PHP](#php)

   4.1 [Основы](#bases1)

   4.2 [Массивы](#array)
   
   4.3 [Технология MVC](#mvc)
   
5. [JavaScript](#js)
   
   5.1 [Основы событий мыши](#base_mouse)

   5.2 [Работа с координатами](#workXY)


---
# CSS <a id="css"></a>
## Подчеркивание <a id="underline"></a>

> тег <\u> в HTML ставит подчеркивание

Cod | Предназначение
:---|:-------------:
text-decoration: underline; | <u>Подчеркивает текст</u>
text-decoration-skip-ink: none; | Подчеркивает текст без пробелов
text-decoration-color: #46C0C1; | Меняет цвет подчеркивания
text-decoration: none; | Не подчеркивает
> Так же можно разширить подчеркивание 
``` text-decoration: underline solid 2px; ```


[Содержание](#content)


# Методология БЭМ <a id="met"></a>
БЭМ | Использование
:---|:-------------:
Блок | имяблока
Элемент __ | имяблока__имяэлемента
Модификатор _ | имяблока_имямодификатора / имяблока__имяэлемента_имямодификатора
Микc | имяблока__имяэлемента имяблока (крч, может быть одновременно и блоком и элементом)
> Создавать блок если код используется повторно, а элемент если фрагмент кода не будет использоваться в дальнейшем
---
```block-name__elem-name--mod-name--mod-val```

* Имена записываются латиницей в нижнем регистре.
* Для разделения слов в именах БЭМ-сущностей используется дефис (-).
* Имя элемента отделяется от имени блока двумя подчеркиваниями (__).
* Булевые модификаторы отделяются от имения блока или элемента двумя дефисами (--).
* Значение модификатора отделяется от его имени двумя дефисами (--).

  [Содержание](#content)

# Git <a id="git"></a>

### Основы <a id="bases"></a>

` git clone (ссылка) ` - скачать репозиторий 

` cd имя_папки ` - вход 

`git add .` - внесение изменений в репозиторий 

` git commit -m "комментарий" `

- если выдает ошибку распознавания:

1) git config --global user.email "почта привязанная к github"

2) git config --global user.name "ник привязанныый к github"

` git push ` - вход в github

[Содержание](#content)

# PHP <a id="php"></a>

## Основы PHP <a id="bases1"></a>
` <?php ... ?> ` - открытие и закрытие тега

` echo "(текст)"; ` - вывод текста 
 
` . "\n" ` - пробел

` "<br>" ` - можно использовать язык html

> точка выполняет роль конкатенации (операция соединения нескольких текстовых строк в одну)

`$a = ...; ` - создание переменной, что ты введешь такой тип данных и будет

``` php
$a = "5"; 
$b = 5;
Вывод: 10
```
- у php слабая типизация поэтому, что ты от него попросишь, то он и сделает

` const A = ...; ` - создание константы 

` echo $b[1]; ` - вывод по индексу (можно вывести только если тип строковый)

## Массивы <a id="array"></a>

` $array = [1,2,3]; ` - создание массива (способ 2)

```
foreach ($array as $element) {
        $sum += $element;
    }
```
- сумма всех элементов массива

```
$max = 0;
    foreach ($array as $element) {
        if ($element > $max) {
            $max = $element;
        }
    }
    echo "<br>Максимальное значение в массиве: $max"
```
- максимальное значение в массиве

```
for ($i = 0; $i < count($array) - 1; $i++) {
        for ($j = 0; $j < count($array) - $i - 1; $j++) {
            if ($array[$j] > $array[$j + 1]) {
                $temp = $array[$j];
                $array[$j] = $array[j +1];
                $array[$j + 1] = $temp;
            }
        }
    }
echo "<br>";
print_r($array);
```
- пузырьковая сортировка

```
$array = [1, 2, 2, 3, 4, 4, 5];
$array_unique = [];

for ($i = 0; $i < count($array); $i++) {
    $is_duplicate = false;

    for ($j = 0; $j < count($array_unique); $j++) {
        if ($array[$i] == $array_unique[$j]) {
            $is_duplicate = true;
            break;
        }
    }
    
    if (!$is_duplicate) {
        $array_unique[] = $array[$i];
    }
}

print_r($array_unique); // Вывод: [1, 2, 3, 4, 5]
```

## Технология MVC <a id="mvc"></a>

1. Создали репозиторий mvc, добавили его в папку `localhost`(необязательно)
2. Здесь создаем project, если выдает ошибку удаляем все нахер из папки project и следуем 3 пункту
```OSPanel
cd domains/localhost
composer create-project --prefer-dist laravel/laravel:^9.0 project
```
3. Из папки `laravel` копируем и вставляем в папку
4. Запускаем OSPanel там свой проект и вводим ссылку `localhost/(name_fail)`
5. Там заходим в `public`, открываем папку через VSCode
6. Открывам PhpMyAdmin, здесь создаем БД с `utf8mb3_general_ci`
7. Заходим в консоль и переходим в project, и прописываем
```
php artisan serve
```
8. Открываем новую консоль, переходим в папку project, здесь прописываем
```
php artisan make:migration create_users_table
```
9. Меняем в `.env` название `DB_DATABASE=` на название БД
10. Заходим в vsc прописываем в папке migrations (если их там несколько, то лишнее нужно удалить) 
```vsc
$table->string('name');
$table->string('email')->unique();
$table->string('password');
```
11. Запускаем в консоли -> (теперь когда зайдем на PhpMyAdmin будут созданы эти столбцы в БД) 
```
php artisan migrate 
```
----

[Содержание](#content)

# JavaScript <a id="js"></a>

## Основы событий мыши <a id="base_mouse"></a>

Типы событий мыши | Использование
:---|:-------------:
`onclick` | Пользователь щелкает по элементу
`oncontextmenu` | Пользователь щелкает правой кнопкой мыши на элементе
`ondblclick` | Пользователь дважды щелкает по элементу
`onmousedown` | Кнопка мыши нажимается на элемент
`onmouseenter` | Указатель мыши перемещается в элемент
`onmouseleave` | Указатель мыши перемещается из элемента
`onmousemove`	| Указатель мыши перемещается над элементом
`onmouseout` | Указатель мыши перемещается за пределы элемента
`onmouseover`	| Указатель мыши перемещается на элемент
`onmouseup` | Кнопка мыши отпускается над элементом

События мыши имеют следующие свойства:

* Кнопка: `button`.

* Клавиши-модификаторы (true если нажаты): `altKey`, `ctrlKey`, `shiftKey` и `metaKey` (Mac).

* Если вы планируете обработать Ctrl, то не забудьте, что пользователи Mac обычно используют Cmd, поэтому лучше проверить `if (e.metaKey || e.ctrlKey)`.

> Пример
```
let con = document.querySelector('div.c')
con.onclick = function test() {
   element.style.width = '200px';
   element.style.height = '200px';
   element.style.backgroundColor = 'red';}
```

## Работа с координатами <a id="workXY"></a>

> Относительно `position: relative` - `clientX/clientY`

> Относительно `position: absolute` - `pageX/pageY`

![Снимок экрана 2024-10-21 234447](https://github.com/user-attachments/assets/95155738-7867-49d1-976b-7660b88a9b7d)

* pageY – координата точки относительно документа осталась без изменений, так как отсчёт по-прежнему ведётся от верхней границы документа (сейчас она прокручена наверх).

* clientY – координата точки относительно окна изменилась (стрелка на рисунке стала короче), так как точка стала ближе к верхней границе окна.

> `elem.getBoundingClientRect()` возвращает объект DOMRect, который содержит размеры элемента и его положение относительно видимой области просмотра

* `offsetTop и offsetLeft` - получение информации о положении на странице

```
document.addEventListener('mousemove', onMouseMove);

// Получаем размеры контейнера
const containerRect = container.getBoundingClientRect();

// Ограничение по X
if (newX < containerRect.left) newX = containerRect.left;
if (newX + draggableRect.width > containerRect.right) {
newX = containerRect.right - draggableRect.width;
}

// Ограничение по Y
if (newY < containerRect.top) newY = containerRect.top;
if (newY + draggableRect.height > containerRect.bottom) {
newY = containerRect.bottom - draggableRect.height;
}
```
```
<input type="file" id="fileInput" multiple />
<script>
document.getElementById('fileInput').addEventListener('change', function() {
    const files = this.files;
    if (files.length > 9) {
        alert("Выберите не более 9 файлов.");
        this.value = ""; // сбросить выбор
    }
});
</script>
```
```
let dragged;

document.addEventListener('dragstart', (event) => {
    dragged = event.target;
});

document.addEventListener('dragover', (event) => {
    event.preventDefault();
});

document.addEventListener('drop', (event) => {
    event.preventDefault();
    const dropzone = document.getElementById('dropzone'); // ваша область
    if (dropzone.contains(event.target)) {
        dropzone.appendChild(dragged);
    }
});
```
