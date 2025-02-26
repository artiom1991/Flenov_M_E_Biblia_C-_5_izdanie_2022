# Фленов Михаил Е. - Библия C# - 5-е издание 2022

## Предисловие:

> В самом начале книги автор рассказал историю появления и эволюции платформы .NET Framework начиная от библиотеки и до ее текущего вида, полноценной платформы которая поддерживает разработку для linux и macOs.
> Так же автор рассказал что за последние 20 лет, платформа .NET несколько раз переписывалась, и меняла названия начиная с .NET Framework, затем .NET Core, а сейчас просто .NET. Так же Microsoft разработала
> удобный обьектно-ориентированый язык программирования C# специально под свою платформу, который был написан вдохновляясь С++ и Delphi.
>
> Сам по себе .NET содержит универсальный набор классов и методов которые имеют одни и те же имена на любом из языков программирования поддерживаемых платформой. Эта платформа полностью ориентирована на обьекты,
> имеет свой сборщик мусора, а так же позволяет осуществлять распределение вычислений при помощи HTTP, XML, SOAP и REST.

## I Введение в .NET

> **_Из чего состоит платформа .NET ?_**
>
> **_Платформа Microsoft .NET:_** cостоит из набора базовых классов и общеязыковой среды выполнения (Common Language Runtime, CLR).
>
> - Cреда выполнения Common Language Runtime (CLR). Она работает поверх ОС, это и есть виртуальная машина, которая обрабатывает IL(промежуточный язык) программы. IL — это аналог бинарного кода для платформы Win32 или
>   байт-кода для виртуальной машины Java. Во время запуска приложения IL-код на лету компилируется в машинный код под то «железо», на котором запущена программа.
> - Базовые классы .NET. Как и библиотеки на других платформах, здесь нам предлагается обширный набор классов, которые упрощают создание приложения. С помощью таких компонентов вы можете строить свои приложения как бы из блоков.
> - Расширенные классы .NET. Также выделяют и более сложные компоненты доступа к базам данных, XML и др.

> **_Сборки:_** это просто файлы, являющиеся результатом компиляции. Наиболее распространены два типа сборок: библиотеки, которые сохраняются в файлах с расширением dll, и исполняемые файлы, которые сохраняются в файлах
> с расширением exe.
>
> Несмотря на то что расширения файлов такие же, как иу Win32-библиотек и приложений, это все же совершенно разные файлы по своему внутреннему содержимому. Программы .NET содержат не инструкции процессора,
> как классические Win32-приложения, а IL-код.Этот код создается компилятором и сохраняется в файле. Когда пользователь запускает программу, то она на лету компилируется в машинный код и выполняется на процессоре.
> Благодаря тому, что IL-код не является машинным, а интерпретируется JIT-компилятором, говорят, что код управляем этим JIT-компилятором. Машинный код выполняется напрямую процессором, и ОС не может управлять этим кодом.
> А вот IL-код выполняется на платформе .NET, и уже она решает, как его выполнять, какие процессорные инструкции использовать, а также берет на себя множество рутинных вопросов безопасности и надежности выполнения.

> После рассмотрения того, чем является платформа .NET автор рассказал что основная IDE для работы с .NET и следствунно C# это Microsoft Visual Code, однако не стал рассматривать ее установку и настройку,
> зато предоставил ссылки на видеоматериалы где он демонстрирует как это сделать. Далее на примере тестового проекта автор показал как создать проект, выбрать версию .NET, разобрал файловую структуру проекта,
> запустил в пороект режиме отладки и продемонстрировал разные виды собрки проекта, а именно: отладочную и релизную.
> Еще он обьяснил что при сборке в режиме "Debug", проект собирается с дополнительной отладочной информацией которая не должна быть в готовом проекте, потому для них существует режим "Release".

> **_Что мне особо понравилось?_**
>
> Автор продемонстрировал инструмент компиляции `csc.exe`, то как его добавить в перемеенное окружение для использование через консоль, а затем как именно скомпилировать файл с расширение .cs в исполняемый файл .exe.
>
> Еще один интересный инструмент платформы .NET который показал автор, это дизасемблер `ildasm.exe`. Чтобы наглядно увидить во что компилируется твой код на C#, можно при помощи этой утилиты проанализировать IL-код скомпелированного файла .exe или .dll.

## II Основы C#

##### Комментарии и переменные

> **_Комментарии:_** это текст, который не влияет на код программы и не компилируется в выходной файл. С помощью комментариев в коде размещается поясяющий текст, для упрощения понимания кода.
> Комментарии бывают однострочными и многострочными.
>
> - Однострочные комментарии начинаются с двух символов `//`, например `// Комментарий`. Все что находится в строке после `//` считается комментарием.
> - Многострочные комментарии в С# заключаются в символы `/*` и `*/`, например `/* Это многострочный комментарий. */`.

> **_Переменная:_** имя которое служит для адресации памяти, называется переменная (именованная ссылка на область в памяти).

> **_Обьявление переменной:_** происходит в виде:`тип имя;`, а чтобы присвоить переменной значение, необходимо использовать конструкцию: `имя = значение;`. Пример обьявления переменной
> `int i;` или можно создать сразу несколько переменных одного типа `int a,b,c;`. Пример присвоения значения переменной `i = 10;`. Пример обьявление переменной с инициализацией `int i = 10;`.

> **_Константы:_** это такие переменные, значения которых нельзя изменить во время выполнения программы. Значение задается только во время их объявления и после этого не изменяется.
> Чтобы переменная стала константой, в объявление нужно добавить ключевое слово `const`, пример `public const double Pi = 3.14;`

> **_null (нулевое значение):_** Ссылочные переменные могут принимать нулевое значение: null. Когда вы присваиваете null, то это как бы указывает на то, что переменная уже ни на что не
> ссылается. Если все переменные, которые ссылались на память, уничтожены, сборщик мусора может освобождать память.

##### Типы данных

> **_Типы данных:_** В .NET используется общая система типов (Common Type System, CTS). Благодаря общности типов в .NET, на каком бы языке вы ни писали программу, типы будут одинаковые, и они
> одинаково будут храниться в памяти, а значит, станут одинаково интерпретироваться программой, и никаких проблем не возникнет. В большинстве языков программирования выделяются два типа данных:
> простые (числа, строки, ...) и сложные (структуры, объекты, ...). В .NET и, соответственно, в С# такое разделение уже не столь четкое. Эта технология полностью объектная, и даже простые типы данных
> в ней являются объектами, хотя вы можете продолжать их использовать как простые типы в других языках. Это сделано для удобства программирования. В .NET типы можно разделить на размерные и ссылочные.
>
> - Размерные типы: это простые типы данных, например: числа, строки и так далее.
> - Ссылочные типы: это объекты, а имя переменной — ссылка на объект.

##### **_Основные типы данных общей системы типов (CTS)_**

| Обьект  | Псевдоним | Описание                                                                                                    |
| ------- | --------- | ----------------------------------------------------------------------------------------------------------- |
| Object  | object    | Базовый класс для всех типов CTS                                                                            |
| String  | string    | Строка                                                                                                      |
| SByte   | sbyte     | 8-разрядное число со знаком. Возможные значения от −128 до 127                                              |
| Byte    | byte      | 8-разрядное число без знака. Значения от 0 до 255                                                           |
| Int16   | short     | 16-разрядное число со знаком. Возможные значения от −32 768 до 32 767                                       |
| UInt16  | ushort    | 16-разрядное число без знака. Значения от 0 до 65 535                                                       |
| Int32   | int       | 32-разрядное число со знаком. Возможные значения от −2 147 483 648 до 2 147 483 647                         |
| UInt32  | uint      | 32-разрядное число без знака. Значения от 0 до 4 294 967 295                                                |
| Int64   | long      | 64-разрядное число со знаком. Возможные значения от −9 223 372 036 854 775 808 до 9 223 372 036 854 775 807 |
| UInt64  | ulong     | 64-разрядное число без знака. Значения от 0 до 18 446 744 073 709 551 615                                   |
| Decimal | decimal   | 128-разрядное число                                                                                         |
| Char    | char      | 16-разрядный символ                                                                                         |
| Single  | float     | 32-разрядное число с плавающей точкой стандарта IEEE                                                        |
| Double  | double    | 64-разрядное число с плавающей точкой                                                                       |
| Boolean | bool      | Булево значение                                                                                             |

> **_int (целое число):_** это целочисленный тип данных, один из самых используемых. Пример `int number = 10;`.

> **_double (дробное число):_** дробный тип данных, или подругому число с плавающей запятой. Пример `double Pi = 3.14;`.

> **_string (строка):_** этот тип данных является экземпляром класса `String` который по своей природе неизменяемый, тоесть после создания его изменить нельзя. Пример `string hello = "Hello";`.
> Хотя визуально при работе с строками можно к переменной со строкой присоединить другую строку, или заменить значение например `hello = "Hello World!"`, но на самом деле создастся новый экземпляр
> класса `String` под который веделется нужный обьем памяти, и уже ей присвоится это значение. Так было задуманно из-за проблем с безопасностью в других языках вроде C++, где был риск залезть
> на используемую другой переменной или вообще другой программой память и перезаписать ее.

> **_char (одиночный символ):_** это одиночный символ, например `char simbol = 'H';`. В отличае от строк, в чар используются одинарные ковычки.

> **_array (массив):_** это список значений, которые последовательно хранятся друг за другом в оперативной памяти компьютера. При обьявлении переменной для хранения массива,
> явно указывается при помощи `[]` что мы будем хранить массив значений определенного типа. Массив обьявляется по этому шаблону `тип[] переменная;` или например для целых
> чисел `int[] numbers;`. На уровне обьявления переменной хранящего массив еще не выделяется память потому, что мы еще не указали сколько элементов этого типа будет храниться,
> для этого переменную нужно проинициализировать. Это делается следующим образом `numbers = new int[3];` где ключевое слово `new` указывает на создание нового экземпляра обьекта
> `массив`, затем указывается тип `int`, и в квадратных скобках длинна массива `[3]`. Чтобы задать значение отдельному элементу, нужно обратиться к переменной и в квадратных скобках
> указать индекс нужного элемента а затем через знак `=` присвоить ему значение, например `numbers[0] = 10`. Все индексы начинаются от 0 и первый элемент списка имеет именно нулевой индекс.
> Так же можно создавать переменные сразу инициализируя значения (задавая стартовые данные), например `int[] numbers = new int[3] {1, 2, 3};`.

> Массивы бывают:
>
> - Одномерный: массив является просто списком значений или если хотиме пример из математики то вектором, пример `int[] numbers = new int[3] {1, 2, 3};`
> - Многомерный: массив можно представить как массивов состоящих из других массивов, или например матрицами значений. Вот пример `int[,] matrix = new int[3,3] { {1, 2, 3}, {4, 5, 6}, {7, 8, 9} };`
>   Доступ к отдельному элементу многомерного массива осуществояется так же как и в одномерном, но прописываются значения (номера индексов элементов) через запятую, начиная от внешнего
>   к внутреннему `matrix[0,0]`, где первый `0` это первый элемент родительского массива, а второй `0` это номер элемента в выбранном массиве.

> **_enum (перечисления):_** это специальный тип данных, который позволяет создавать набор именованных констант. Перечисления используются для представления фиксированного набора значений, что
> делает код более читаемым и удобным для работы. Пример: `enum имя { Значения через запятую };` или `enum WeekDays { Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday };` или
> `enum WeekDays { Monday = 1, Tuesday=2, Wednesday=3, Thursday=4, Friday=5, Saturday=6, Sunday=7 };`.

##### Пространство имен

> **_Пространство имен:_** это определенная область, внутри которой все имена должны быть уникальными. И именно благодаря использованию пространства имен уникальность переменных должна обеспечиваться только
> внутри — т. е. в разных модулях могут иметься переменные с одинаковыми именами. Пример пространства имен `Windows` Windows.FindFirst или для пространства имен `Linux` Linux.FindFirst.
> Это как названия улиц. Вот пример, улица — Королева, а где она находится? Очень сложно с ходу дать правильный ответ, потому что улицу с таким названием можно найти в разных городах, так что как раз
> название города может выступать здесь в качестве пространства имен. Вот пример использования пространства имен с `Москва` - Москва.Королева. В .NET все: классы, переменные, структуры и т. д. — разбито
> по пространствам имен, например: `namespace Имя { Определение типов }`.
> Чтобы подключить пространство имен нужно использовать ключевое слово `using`, например `using System;`.

##### Операции над переменными

> **_Математические операторы:_**
>
> - Сложение `+`, пример `number + number`
> - Вычитание `-`, пример `number - number`
> - Умножение `*`, пример `number * number`
> - Деление `/`, пример `number / number`
> - Инкремента `++`, постфиксный пример `number++`, или префиксный пример `++number`, аналог `number = number + 1`
> - Декремента `--`, постфиксный пример `number--`, или префиксный пример `--number`, аналог `number = number - 1`
> - Прибавить к переменной `+=`,пример `number += 2`, аналог `number = number + 2`
> - Отнять у переменной `-=`,пример `number -= 2`, аналог `number = number - 2`
> - Умножить переменную на значение `*=`, пример `number = number * 2`
> - Разделить переменную на значение `/=`, пример `number /= 3`, аналог `number = number / 3`

> **_Конкатенация:_** это когда одна строка добавляется (не прибавляется математически, а добавляется/присоединяется) в конец другой строки.
> пример: `"Hello" + " " + "World" + "!" = "Hello World!"`.

##### Условия, операторы сравнения и логические операторы

> **_if (условный оператор):_** Для создания логики приложения в C# есть оператор if, синтаксис которого в общем виде таков:`if (Условие) { Действие } else { Действие }`

> **_Операторы сравнения:_** результатом такого сравнения будет логический тип данных `troe` или `false`, тоесть истиное или ложное значение.
>
> - Больше `>`, пример `x > y`
> - Меньше `<`, пример `x < y`
> - Больше либо равно `>=`, пример `x >= y`
> - Меньше либо равно `<=`, пример `x <= y`
> - Равно `==`, пример `x == y`
> - Не равно `!=`, пример `x != y`

> **_Логические операторы:_**
>
> - И `&&`, пример `x == true && y == true`, где условие будет верно если оба подвыражения будут верны
> - ИЛИ `||`, пример `x == true || y == true`, где условие будет верно если одно из подвыраженйи верно
> - НЕ `!`, пример `!true` равно `false` потому что `!` инвертирует значение

> **_switch (условный оператор):_** `switch (переменная) {case Значение1: Действия; break; case Значение2: Действия; break; default: Действия по умолчанию; break; }`

> **_Сокращенная проверка (тернарный оператор):_** `Условие ? Действие 1 : Действие 2`

##### Циклы

> **_for (цикл):_** `for (Инициализация; Условие; Порядок выполнения) {Действие;}`
>
> - Инициализация — начальное значение переменной счетчика
> - Условие — пока это условие возвращает истину, действие будет выполняться
> - Порядок выполнения — команда, которая должна увеличивать счетчик.

> **_while (цикл):_** `while (условие) {Действие;}`

> **_do while (цикл):_** `do {Действие;} while (условие);`

> **_foreach (цикл):_** `foreach (тип переменная in массив) { Действие; }`

> **_break (оператор управления циклом):_** как только программа встречает этот оператор, она прерывает цикл.

> **_continue (оператор управления циклом):_** прерывает текущий шаг цикла и заставляет перейти на выполнение следующего шага.
