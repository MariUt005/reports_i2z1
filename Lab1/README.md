# Введение в R


## Цель

1.  Развить практические навыки использования языка программирования R
    для обработки данных
2.  Развить навыки работы в Rstudio IDE:

-   установка пакетов
-   работа с проектами в Rstudio
-   настройка и работа с Git

1.  Закрепить знания базовых типов данных языка R и простейших операций
    с ними

## ️Исходные данные

1.  Ноутбук c Windows 11 и установленным Git, R и RStudio
2.  Программный пакет swirl

## ️Ход работы

1.  Установить интерпретатор R
2.  Установить Rstudio IDE
3.  Установить программный пакет swirl:
    -   через интерфейс Rstudio IDE
    -   или функцией R install.packages(“swirl”)
4.  Запустить задание с помощью swirl::swirl()
5.  Выбрать из меню курсов 1. R Programming: The basics of programming
    in R
6.  Запустить подкурсы и выполнить:
    -   базовые структурные блоки (Basic Building Blocks)
    -   рабочие пространства и файлы (Workspace and Files)
    -   последовательности чисел (Sequences of Numbers)
    -   векторы (Vectors)
    -   пропущенные значения (Missing Values)
7.  Составить отчет и выложить его и исходный qmd/rmd файл в свой
    репозиторий

## Содержание ЛР

### Шаг 1

Установлены R 4.4.1 и RStudio.

![](images/1.png)

### Шаг 2

Установка программного пакета swirl:

``` r
install.packages("swirl")
```

### Шаг 3

Запуск задания

``` r
swirl::swirl()
```

### Шаг 4

Выбрарать из меню курсов 1. R Programming: The basics of programming in
R.

Запуск и выполнение подкурсов:

-   базовые структурные блоки (Basic Building Blocks)

``` r
5 + 7
```

    [1] 12

``` r
x <- 5 + 7
```

``` r
x
```

    [1] 12

``` r
y <- x - 3
```

``` r
y
```

    [1] 9

``` r
z <- c(1.1, 9, 3.14)
```

``` r
?c
```

    запускаю httpd сервер помощи... готово

``` r
z
```

    [1] 1.10 9.00 3.14

``` r
c(z, 555, z)
```

    [1]   1.10   9.00   3.14 555.00   1.10   9.00   3.14

``` r
z * 2 + 100
```

    [1] 102.20 118.00 106.28

``` r
my_sqrt <- sqrt(z - 1)
```

``` r
my_sqrt
```

    [1] 0.3162278 2.8284271 1.4628739

``` r
my_div <- z / my_sqrt
```

``` r
my_div
```

    [1] 3.478505 3.181981 2.146460

``` r
c(1, 2, 3, 4) + c(0, 10)
```

    [1]  1 12  3 14

``` r
c(1, 2, 3, 4) + c(0, 10, 100)
```

    Warning in c(1, 2, 3, 4) + c(0, 10, 100): длина большего объекта не является
    произведением длины меньшего объекта

    [1]   1  12 103   4

``` r
z * 2 + 1000
```

    [1] 1002.20 1018.00 1006.28

``` r
my_div
```

    [1] 3.478505 3.181981 2.146460

-   рабочие пространства и файлы (Workspace and Files)

``` r
getwd()
```

    [1] "C:/Users/maria/Documents/reports_i2z1/Lab2"

``` r
ls()
```

    [1] "my_div"  "my_sqrt" "x"       "y"       "z"      

``` r
x <- 9
```

``` r
ls()
```

    [1] "my_div"  "my_sqrt" "x"       "y"       "z"      

``` r
list.files()
```

    [1] "images"           "README.ipynb"     "README.md"        "README.qmd"      
    [5] "README.rmarkdown"

``` r
?list.files
```

``` r
args(list.files)
```

    function (path = ".", pattern = NULL, all.files = FALSE, full.names = FALSE, 
        recursive = FALSE, ignore.case = FALSE, include.dirs = FALSE, 
        no.. = FALSE) 
    NULL

``` r
old.dir <- getwd()
```

``` r
dir.create("testdir")
```

``` r
setwd("testdir")
```

``` r
file.create('mytest.R')
```

    [1] TRUE

``` r
list.files()
```

    [1] "images"           "mytest.R"         "README.ipynb"     "README.md"       
    [5] "README.qmd"       "README.rmarkdown" "testdir"         

``` r
file.exists('mytest.R')
```

    [1] TRUE

``` r
file.info('mytest.R')
```

             size isdir mode               mtime               ctime
    mytest.R    0 FALSE  666 2024-09-21 14:08:42 2024-09-21 14:08:42
                           atime exe
    mytest.R 2024-09-21 14:08:42  no

``` r
file.rename('mytest.R', 'mytest2.R')
```

    [1] TRUE

``` r
file.copy('mytest2.R', 'mytest3.R')
```

    [1] TRUE

``` r
file.path('mytest3.R')
```

    [1] "mytest3.R"

``` r
file.path('folder1', 'folder2')
```

    [1] "folder1/folder2"

``` r
?dir.create
```

``` r
dir.create(file.path('testdir2', 'testdir3'), recursive = TRUE)
```

``` r
setwd(old.dir)
```

-   последовательности чисел (Sequences of Numbers)

``` r
1:20
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

``` r
pi:10
```

    [1] 3.141593 4.141593 5.141593 6.141593 7.141593 8.141593 9.141593

``` r
15:1
```

     [1] 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1

``` r
?`:`
```

``` r
seq(1, 20)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

``` r
seq(0, 10, by=0.5)
```

     [1]  0.0  0.5  1.0  1.5  2.0  2.5  3.0  3.5  4.0  4.5  5.0  5.5  6.0  6.5  7.0
    [16]  7.5  8.0  8.5  9.0  9.5 10.0

``` r
my_seq <- seq(5, 10, length=30)
```

``` r
length(my_seq)
```

    [1] 30

``` r
1:length(my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

``` r
seq(along.with = my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

``` r
seq_along(my_seq)
```

     [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
    [26] 26 27 28 29 30

``` r
rep(0, times = 40)
```

     [1] 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
    [39] 0 0

``` r
rep(c(0, 1, 2), times = 10)
```

     [1] 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2 0 1 2

``` r
rep(c(0, 1, 2), each = 10)
```

     [1] 0 0 0 0 0 0 0 0 0 0 1 1 1 1 1 1 1 1 1 1 2 2 2 2 2 2 2 2 2 2

-   векторы (Vectors)

``` r
num_vect <- c(0.5, 55, -10, 6)
```

``` r
tf <- num_vect < 1
```

``` r
tf
```

    [1]  TRUE FALSE  TRUE FALSE

``` r
num_vect >= 6
```

    [1] FALSE  TRUE FALSE  TRUE

``` r
my_char <- c("My", "name", "is")
```

``` r
my_char
```

    [1] "My"   "name" "is"  

``` r
paste(my_char, collapse = " ")
```

    [1] "My name is"

``` r
my_name <- c(my_char, "Maria")
```

``` r
my_name
```

    [1] "My"    "name"  "is"    "Maria"

``` r
paste(my_name, collapse = " ")
```

    [1] "My name is Maria"

``` r
paste("Hello", "world!", sep = " ")
```

    [1] "Hello world!"

``` r
paste(1:3, c("X", "Y", "Z"), sep = "")
```

    [1] "1X" "2Y" "3Z"

``` r
paste(LETTERS, 1:4, sep = "-")
```

     [1] "A-1" "B-2" "C-3" "D-4" "E-1" "F-2" "G-3" "H-4" "I-1" "J-2" "K-3" "L-4"
    [13] "M-1" "N-2" "O-3" "P-4" "Q-1" "R-2" "S-3" "T-4" "U-1" "V-2" "W-3" "X-4"
    [25] "Y-1" "Z-2"

-   пропущенные значения (Missing Values)

``` r
x <- c(44, NA, 5, NA)
```

``` r
x * 3
```

    [1] 132  NA  15  NA

``` r
y <- rnorm(1000)
```

``` r
z <- rep(NA, 1000)
```

``` r
my_data <- sample(c(y, z), 100)
```

``` r
my_na <- is.na(my_data)
```

``` r
my_na
```

      [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE  TRUE  TRUE
     [13] FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE  TRUE FALSE  TRUE  TRUE FALSE
     [25]  TRUE  TRUE  TRUE  TRUE  TRUE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
     [37] FALSE  TRUE FALSE  TRUE FALSE FALSE FALSE  TRUE  TRUE  TRUE FALSE FALSE
     [49] FALSE  TRUE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE  TRUE FALSE FALSE
     [61] FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE  TRUE  TRUE  TRUE FALSE
     [73]  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE
     [85] FALSE FALSE  TRUE FALSE  TRUE  TRUE  TRUE FALSE  TRUE FALSE FALSE  TRUE
     [97]  TRUE FALSE  TRUE  TRUE

``` r
my_data == NA
```

      [1] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
     [26] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
     [51] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA
     [76] NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA NA

``` r
sum(my_na)
```

    [1] 41

``` r
my_data
```

      [1]  0.4349625397  0.8624046063 -1.3924248663 -0.5017409606  1.2056105382
      [6]  0.9692201966 -0.5708382661  0.0007806306            NA -0.0325718804
     [11]            NA            NA  1.0068967844 -0.6329328691            NA
     [16]            NA  0.1393176255  0.1931176111 -0.3369194779            NA
     [21]  0.9798038647            NA            NA  0.4642347028            NA
     [26]            NA            NA            NA            NA -0.1009152058
     [31] -0.6551047650            NA -1.6251286529 -0.1499845730  1.8861291562
     [36] -0.9291835909 -0.2255115498            NA -2.5693592591            NA
     [41]  0.8918296143  0.9406712954 -1.3147497579            NA            NA
     [46]            NA  0.5135621115 -1.6337869706  0.8153877033            NA
     [51] -1.5450939567  1.1695228564            NA            NA -0.7939310053
     [56]  1.6473996055  1.8169093279            NA -0.4587164074 -0.7324687174
     [61]  0.7572046436  1.4256181530 -0.5858426857  2.1684800798 -1.1799165960
     [66]            NA  0.0449050198  1.7611068137            NA            NA
     [71]            NA -0.5115697174            NA            NA            NA
     [76]            NA  0.9329679310 -1.1952209899  0.3972051923  0.6761766287
     [81] -0.2807016335 -0.2979879812            NA -2.1630827910 -0.4782261607
     [86]  0.4021648612            NA  0.7080772345            NA            NA
     [91]            NA -0.0874733969            NA  1.1841954152  0.5777580910
     [96]            NA            NA -1.1295839350            NA            NA

``` r
0 / 0
```

    [1] NaN

``` r
Inf - Inf
```

    [1] NaN

## Оценка результатов

Задача выполнена при помощи RStudio, удалось познакомится с функционалом
и особенностями языка программирования R.

## Вывод

В данной работе успешно удалось познакомиться с языком R и выполнить
учебные задания по swirl.
