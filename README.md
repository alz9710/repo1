# repo1
Многопоточная программа парсинга текстового файла.

Файлы:
* parse.c -- исходный код на си разделяемой библиотеки парсинга текстового файла
* main.py -- скрипт на питоне вызова и теста библиотеки парсинга
* main.c -- исходный код на си программы вызова библиотеки парсинга
* log -- лог скрипта main.py

# Интерпретация лог-файла log

read time: время чтения с носителя информации в чанки (в миллисекундах)

parse time: время парсинга с чанков в массив вещественных чисел (в миллисекундах)

total time: суммарное время парсинга (в миллисекундах)

total floats read: кол-во прочтенных вещественных чисел

check: проверка массива распарсеных чисел, верно ли распарсены числа

# Запуск

```
make
python main.py
```