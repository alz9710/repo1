# repo1

Многопоточная программа парсинга текстового файла.

# Структура исходников

В корневом каталоге находятся файлы:

* `parse.c` -- исходный код на си разделяемой библиотеки парсинга текстового файла
* `main.py` -- скрипт на питоне вызова и теста библиотеки парсинга
* `main.c` -- исходный код на си программы вызова библиотеки парсинга
* `py_*.log` -- лог скрипта main.py
* `c_*.log` -- лог программы main.с

## Интерпретация лога скрипта main.c

```
-------------------------
run test
<начало работы>

thread: <номер потока>

subchunk: offset <смещение подчанка subchunk внутри чанка>, size_lines <размер подчанка в строках>

chunk line read: <сторка чанка, которая парсится>

floats read: <кол-во распарсенных чисел подчанка>
<вывод распарсенных чисел подчанка>

write offset: <смещение положения записи распарсенных чисел подчанка в массив распарсенных чисел arr>

total floats read: <кол-во распарсенных чисел в массиве arr>
<вывод распарсенных чисел массива arr>

read time: <время чтения с носителя информации в чанки (в миллисекундах)>

parse time: <время парсинга с чанков в массив вещественных чисел (в миллисекундах)>

total time: <суммарное время парсинга (в миллисекундах)>
```

## Интерпретация лога скрипта main.py

```
read time: <время чтения с носителя информации в чанки (в миллисекундах)>

parse time: <время парсинга с чанков в массив вещественных чисел (в миллисекундах)>

total time: <суммарное время парсинга (в миллисекундах)>

total floats read: <кол-во прочтенных вещественных чисел>

check: <проверка массива распарсеных чисел, верно ли распарсены числа>
```

## Компиляция

```
$ make
```

## Запуск

Запуск тестов на си:
```
$ cd repo1/
$ export LD_LIBRARY_PATH=$PWD:$LD_LIBRARY_PATH
$ ./test0.out
$ ./test1.out
```