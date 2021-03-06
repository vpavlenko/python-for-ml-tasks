1. def, return
--------------

Работаем с датасетом Japanese Credit Screening: [crx.data](crx.data.txt)

Напишите функцию `read_dataset(filename)`, которая принимает на вход имя файла, а возвращает массив x из наборов фич и массив y ответов. Считайте, что ответы в нашем датасете хранятся в последнем столбце. Пример, если в файле было бы только две строки датасета:

    x = [['b', 30.83, 0, 'u', 'g', 'w', 'v', 1.25, 't', 't', 1, 'f', 'g', 202, 0],
         ['a', 58.67, 4.46, 'u', 'g', 'q', 'h', 3.04, 't', 't', 6, 'f', 'g', 43, 560]]
    y = ['+', '+']

Имейте ввиду, что у списков бывают срезы:

    >>> ['a', 'b', 'c', 'd', 'e'][:2]
    ['a', 'b']
    >>> ['a', 'b', 'c', 'd', 'e'][-1:]
    ['e']



2. collections.Counter
----------------------

Посчитайте, сколько раз принимается каждое возможное значение в столбце 6. В первой строке там написано 'w'.

Для этого прочитайте примеры использования `collections.Counter` во встроенной справке. Наберите в интерактивном режиме:
`help('collections.Counter')`



3. max(key=...)
---------------

Найдите строчку, на которой достигается максимальное произведение значений в столбцах 2 и 8. Это называется в литературе "argmin".

    >>> a = ['abcd', 'abacaba', 'bc', 'def', 'bbbb']
    >>> sorted(a, key=len)
    ['bc', 'def', 'abcd', 'bbbb', 'abacaba']
    >>> sorted(a, key=lambda x: x[1])
    ['abcd', 'abacaba', 'bbbb', 'bc', 'def']
    >>> min(a, key=lambda x: x[::-1])
    'abacaba'
    >>> max(a, key=lambda x: x[::-1])
    'def'
    >>> sorted(a, key=lambda x: len(set(x)))
    ['bbbb', 'bc', 'abacaba', 'def', 'abcd']



4. open(encoding=...)
---------------------

Попробуйте открыть файлы anna_*.txt без параметра encoding и прочитать их содержимое. 
Попробуйте в функции open() указывать параметр encoding='utf-8' и encoding='windows-1251'

Кстати, когда вы пишете скрипт и в нём используете хитрые символы вроде кириллицы, то указывайте в начале его скрипта его кодировку.
Например, напишите в первой строке:
-*- coding: windows-1251 -*-



5. class
--------

Напишите класс `Classifier`, который имеет методы `train(x, y)` и `predict_all(x) -> y`. Ваши классификаторы будут наследоваться от класса `Classifier` 
и имплементировать методы `train(x, y)` и `predict_single(x_i)`. В базовом классе `Classifier` опишите, что `predict_all(x)` вызывает для каждого объекта функцию `predict_single(x_i)`, которая будет определена в потомке.

Напишите классификатор 1NN, принимающий в конструкторе список полей, по которым делать 1NN. Метрику возьмите равномерной евклидовой.

Напишите функцию `cross_validation(classifier, x, y, k)`, которая делает k-fold-кросс-валидацию на данных x, y. Выведите min, avg и max на терминал.
