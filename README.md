# CV2023_lab1
Команда:
* Горбунова Екатерина 
* Горцуева Александра
* Чернышев Артем
* Терешин Данил
* Никурашин Алексей
#  Задача выделения бинарной маски переднего плана
## Датасет
Расположен в архиве `Lab1.zip`

Включает в себя:
* 100 изображений кошек и собак 
* 100 тринарных масок для данных изображений (в ходе решения задачи потребуется перевести тринарные маски в бинарные, пример перевода в файле `metric_evaluation.py`)

Данные отобраны из датасета [The Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/)

## Описание задачи
* Язык программирования - `Python`
* Выделение бинарной маски изображения может быть выполнено с помощью различных математических операций (самописных или готовых решений из сторонних библиотек), без использования методов машинного обучения

* В файле `solution_example.py` реализовать функцию `get_foreground_mask()`

## Метрики
**Метрика точности**
* В качестве метрики оценки результата используется IoU (Intersection over Union), расчитанная для класса foreground
* Вычисление метрики выполняется последовательно для каждого изображения в файле `metric_evaluation.py` в функции `evaluate_iou()`

![image_2023-09-17_20-47-39](https://learnopencv.com/wp-content/uploads/2022/12/feature-image-iou-1-1024x292.jpg)

## Baseline
* IoU вычисляется для каждого изображения, затем определяется среднее значение
* Основные шаги:
  * Поиск градиентов
  * 
* При помощи медотов указанных в таблице лучшее значение метрики IoU достигло: 0.91;


| Методы   | Ссылка на решение | Результат | Скорость выполнения |
|----------|-------------------|-----------|---------------------|
| Sobel, morphological, threshold, findContours                | [ноутбук](https://colab.research.google.com/drive/1jLoLhwLoiuEl7kbHgRL-dhrnMXl-1vUr?usp=sharing)           | 0,9068 |1,6 С/Мп |
| Sobel, morphological, threshold, GaussianBlur, binary_closing| [ноутбук](https://colab.research.google.com/drive/1JobD_DqQEZG-Pp-Ig2LDvTboh7xykv3T#scrollTo=HBMzR7U74fTz) | 0,8380 |1,4 С/Мп |
| Laplacian, threshold, Morphological, GaussianBlur            | [ноутбук](https://colab.research.google.com/drive/1-fgFF5tkys7SLSuWoNv1q6PvDPCR2l3z?usp=sharing)           | 0,8188 |1,3 C/Мп |




