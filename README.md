# repo1

Многопоточная программа парсинга текстового файла.

## Структура репозитория

В корневом каталоге находятся файлы:

* Исходный код `parse.c` на си разделяемой библиотеки парсинга
* `main.py` скрипт на питоне вызова и теста библиотеки парсинга
*  Программа `main.c` вызывает библиотеку парсинга, чтобы включать отладочную информацию и ассерты в библиотеке и парсить файл `test.txt`
*  Данные `test.txt`
*  Логи `py_*.log` скрипта `main.py`
*  Логи `c_*.log` программы `main.с`

## Интерпретация лога программы main.c

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

## Запуск

Программа на си:
```
$ make
$ ./main.out
```

Скрипт на питоне:
```
$ make shared
$ python main.py
```