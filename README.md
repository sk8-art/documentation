

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

   4.4 [Запросы](#zap)
   
5. [JavaScript](#js)
   
   5.1 [Основы событий мыши](#base_mouse)

   5.2 [Работа с координатами](#workXY)

6. [Задачи](#tasks)
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

` define ("PI", 3.14) ` - константа 

``` php
$a = "5"; 
$b = 5;
Вывод: 10
```
- у php слабая типизация поэтому, что ты от него попросишь, то он и сделает

` const A = ...; ` - создание константы 

` echo $b[1]; ` - вывод по индексу (можно вывести только если тип строковый)

` strpos($a, " ") ` - поиск чего либо, то есть в переменной а он ищет пробел

` substr($a, 0, $b) ` - здесь из переменной a, начиная с 0 до позиции b извлекаем все

` strtoupper($a) ` - помешает в верхний регистр (то есть капсом)

` strtolower($a) ` - помещает в нижний регистр (то есть все становится маленькими буквами)

` count($array) ` - считает кол-во элементов в массиве

` count_chars($str, 1) ` - функция возвращает массив, содержащий только уникальные символы

##Работа с файлами

` file_put_contents("./name_fail.txt", "что_хотим_сюда_добавить") ` - добавлене в файл текст

` file_get_contents ` - получение информации

` file_put_contents("./text.txt", $username . " "  , FILE_APPEND); ` - не перезаписывает полностью файл, а добавляет (в данном случае добавляет вводимое имя)

` date("Y-m-d") ` - дата год/месяц/день

` date("H-i-s") ` - время часы/минуты/секунды

```
$oleg = ["name" => "oleg", "age"=>"27"]; ` - ассоциации
echo $oleg["name"];
```
- ассоциации

 
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
2. Здесь создаем project, если выдает ошибку удаляем все нахер из папки project и следуем 3 пункту, если не выдает то пропускаем его
```OSPanel
cd domains/localhost
composer create-project --prefer-dist laravel/laravel:^9.0 project
```
3. Из папки `laravel` копируем и вставляем в папку
4. Запускаем OSPanel там свой проект и вводим ссылку `localhost/(name_fail)`
5. Там заходим в `public`, открываем папку через VSCode
> (если не работает то удалить в папке database/migrations все кроме user, в папке app/http/controllers все кроме controller и в папке app/models все удалить)
> и нужно название в .env бд поменять
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
12.
```
php artisan make:model User
```
- создание новой модели

13.
```
 php artisan make:controller ProductController
```
- создание контроллера
14.
```
use App\Model\User;

class UserControllerr extends Controller
{
    //Валедация
    public function store(Request $request) {
        $request->validate([
            'name' => 'required|string|max:255',
            'email' => 'required|string|email|max:255|unique:users',
            'password' => 'required|string|min:8|confirmed',
        ])
        $user = User::create($request->all());

        return responce()->jcon($user, 201);
    }

    public function index() {
        return User::all();
    }
    //Поиск по id
    public function show($id) {
        return User::findOrFail($id);
    }

    public function update(Request $request, $id) {
        $user = User::FindOrFail($id);

        $user->update($request->all());

        return respone()->json(null, 204);
    }

    public function destroy($id) {
        User::destroy($id);
        return responce()->json(null, 204);
    }
}
```

## Запросы <a id="zap"></a>

`get` - получение информации

`post` - отправление информации

`put` - изменение информации

`delete` - удаление информации

1. Заходим в postman (в папке C) пишем `http://localhost/project/public/api/users` должно вывести `[]`

2. Меняем get на post, заходим в Body > form-data, указываем name, email, password

3. Выбираем delete, в ссылке пишем id который хотим удалить, например `http://localhost/project/public/api/users/1`
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


# Задачи <a id="tasks"></a>

```
$age = $_POST["age"];

    $a1 = $age % 10;
    $a2 = $age % 100;
    
    if ($a1==1 && $a2 != 11) {
        $age1 = "год";
    } else if ($a1 >= 2 && $a1 <=4 && ($a2 < 12 || $a2 > 14)) {
        $age1 = "года";
    } else {
        $age1 = "лет";
    }
echo "hey, $username" . "<br> " . "Тебе уже " . $age . " " . $age1;
``` 
> приветствие в зависимости от того сколько ему - лет/год/года
```
$fullname = "Oleg Olegov";
function qwe ($fullname) {
    $full = strpos($fullname, " ");

    $name = substr($fullname, 0, $full); //здесь из fullname начиная с 0 до позиции пробела
    echo strtoupper($name);
    echo"<br>";

    $last = substr($fullname, $full + 1);
    echo strtolower($last);
    echo "<br>";
    
    $in1 = strtoupper(substr($fullname, 0, 1)); //откуда, что, сколько
    $in2 = strtoupper(substr($fullname, $full + 1, 1));
    echo $in1 . $in2;
    echo "<br>";
}
qwe($fullname);
```
> функция, которая делает имя олег маленькими буквами, а фамилию капсом
```
$array = [1, 2, 3, 2, 4, 5, 1, 6, 3];
$unique_array = [];

for ($i = 0; $i < count($array); $i++) {
    $bool = false;
    for($j = 0; $j < count($unique_array); $j++) {
       if ($array[$i] == $array[$j]) {
        $bool = true;
        break;
       }
    }
    if (!$bool) {
        $unique_array[] = $array[$i];
    }
}

for ($n = 0; $n < count($unique_array); $n++) {
	echo $unique_array[$n] . "<br>";
}
```
> удаление повторяющихся элементов из числового массива

```
$max = 0;
$array_max = [12, 45, 7, 45, 34, 5];

function findSecondLargest($numbers) {

    $max = 0;
    for ($i = 1; $i < count($numbers); $i++) {
        if ($numbers[$i] > $max) {
            $max = $numbers[$i];
        }
    }

    $secondLargest = 0;
    $secondLargestCount = 0;

    for ($i = 0; $i < count($numbers); $i++) {
        if ($numbers[$i] < $max) {
            if ($secondLargest === 0 || $numbers[$i] > $secondLargest) {
                $secondLargest = $numbers[$i];
                $secondLargestCount = 1;
            } else if ($numbers[$i] == $secondLargest) {
              $secondLargestCount++;
            }
        }
    }
    if($secondLargestCount > 1){
      return findSecondLargest(array_unique($numbers));
    }

    return $secondLargest;
}
$secondLargest = findSecondLargest($array_max);

if ($secondLargest !== 0) {
  echo $secondLargest;
}
```
> определение второго наибольшего числа в массиве
```
function anana ($str_1, $str_2) {
    if (count_chars($str_1, 1) == count_chars($str_2, 1)) {
        echo 'yes';
    }
    else {
        echo 'no';
    }
}
anana('efef', 'fefe');
```
> проверка на анаграммы

```
$fullname = file_get_contents("./text.txt");

function fam($a) {
    $full = strpos($a, " ");
    $surname = substr($a, 0, $full);
    echo $surname;
}
fam($fullname);
echo "<br>";

function name($a) {
    $full = strpos($a, " ");
    $name = substr($a, $full + 1);
    echo $name;
}
name($fullname);
echo "<br>";

function ini($fullname) {
    echo $fullname[0] . $fullname[strpos($fullname, " ") + 1];
}
ini($fullname);
```
> функции для вывода по отдельности фамилии, имени и отчестве
```
$oleg = ["name" => "oleg", "age"=>"27"];
$danil = ["name" => "danil", "age"=>"14"];
$mihail = ["name" => "micha", "age"=>"32"];

echo $oleg["name"] . " " . $oleg["age"];
echo "<br>";
echo $danil["name"] . " " . $danil["age"];
echo "<br>";
echo $mihail["name"] . " " . $mihail["age"];
```
> ассоциации, вывод имени и возраста
```
