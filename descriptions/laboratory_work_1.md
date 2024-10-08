# Лабораторная работа 1: «Метод обратного распространения ошибки»

## Цели работы

**Цель** — изучить метод обратного распространения ошибки для обучения глубоких нейронных сетей на примере двухслойной полносвязной нейронной сети (один скрытый слой).

## Задачи работы

Выполнение работы предполагает решение следующих задач:

1. Изучение общей схемы работы метода обратного распространения ошибки с помощью стохастического градиентного спуска.
2. Вывод математических формул для вычисления градиентов функции ошибки по параметрам нейронной сети и формул коррекции весов.
3. Реализация и тестирование метода обратного распространения ошибки для классификации рукописных цифр из набора данных [MNIST](https://www.kaggle.com/datasets/hojjatk/mnist-dataset).


Конфигурация нейронной сети:

1. Входной слой содержит `w x h` нейронов, что соответствует разрешению одноканального изображения (для изображений в базе MNIST составляет 28x28).
2. Выходной слой содержит `k` нейронов, что соответствует количеству классов изображений (для задачи классификации рукописных цифр MNIST – 10 классов).
3. Скрытый слой содержит `s` нейронов (параметр).
4. Скорость обучения (learning rate), размер пачки данных (batch size), количество эпох являются параметрами метода обучения.
5. В качестве функции активации на скрытом слое используется функция ReLU. В качестве функции активации на выходном слое используется функция softmax. Входной слой не содержит функцию активации.
6. В качестве функции ошибки используется кросс-энтропия. Функция активации softmax вместе с функцией ошибки кросс-энтропия упрощают вывод формул.
7. Набор параметров для демонстрации работы нейронной сети (и выложенные материалы и демонстрации в т/к выполняется на данных параметрах):
    - Размер пачки может меняться от 8 до 64 изображений (в зависимости от доступного объема памяти).
    - Скорость обучения - 0.1.
    - Количество скрытых нейронов `s` - 300.
    - Количество эпох – 20.

## Требования к результатам выполнения работы

1. Требования к структуре и содержимому Jupyter Notebook:

   - Загрузить и проверить данные (необходимо обеспечить демонстрацию избранных изображений и меток классов для подтверждения корректности загрузки и совпадения размерностей)
   - По окончании каждой эпохи в процессе обучения модели выводится ошибка классификации на тренировочном наборе данных и время выполнения эпохи.
   - После обучения выводится ошибка классификации на тестовом наборе данных.

2. Для контрольных значений параметров достигнута точность классификации на тестовых данных, сравнимая с точностью, которую выдают стандартные инструменты глубокого обучения (например, библиотеки Keras или PyTorch). Подсказка: Точность будет ~95% с ***неправильной*** инициализации весов, ожидается результат ***лучше***.

3. Запуск необходимо выполнить в процессе очной сдачи. Время обучения на контрольном наборе параметров не должно превышать время, выделенное на сдачу работу одним студентом (~7-15 минут).

4. Реализация не должна содержать использование tensorflow, keras, pytorch или иных фреймворков глубокого обучения. Допускается использование библиотек, таких как NumPy, Matplotlib и других классических библиотек.

## Оценивание

Максимальное количество баллов - 30 баллов:
1. 5 баллов за подтверждение загрузки и проверки корректности данных.
2. 10 баллов за реализацию и подтверждение корректности метода обратного распространения ошибки.
3. 15 баллов за обсуждение и демонстрацию понимания основных концепций работы.