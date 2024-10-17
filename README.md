

# Содержание <a id="content"></a>
---
1. [CSS](#css)
   
    1.1 [Подчеркивание](#underline)
2. [Методология БЭМ](#met)
3. [Git](#git)
4. [PHP](#php)
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

### Основы 

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

## Массивы

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

## Технология MVC

Создали репозиторий mvc, добавили его в папку localhost, из папка laravel копируем и вставляем в папку репозитория. Запускаем OSPanel там свой проект и вводим ссылку localhost/(name_fail). Там заходим в public.
----

```  Консоль OSPanel
cd domains/localhost
composer create-project --prefer-dist laravel/laravel project
 ```

[Содержание](#content)
