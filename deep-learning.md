Oleksandr, [8 сент. 2020 г., 21:14:10]:
Тензор содержащий единственное число называется скаляром или тензором нулевого ранга

определить кол-во тензора в Numpy можно с помощью атрибута ndim

скалярный тензор имеет 0 осей

кол-во осей тензора также называют его рангом

вектор - одномерный массив чисел или тензор первого ранга

> x = np.array([1,2,3])

массив векторов - матрица или двумерный тензор

если упаковать матрицы в массив получится тензор третьего ранга, его можно представить как числовой куб

Тензор определяется тремя ключевыми атрибутами

- количество осей (ранг) - ndim
- форма (shape)- кортеж целых чисел описывающих количество измерений на каждой оси тензора 
- Тип данных (dtype)

операция выбора конкретного элемента в тензоре называется получением среза тензора

извлечь цифры с 10 до 100 (100 не включается)

> my_slice = train_images[10:100]

Это эквивалентно более подробной форме записи в которой определяются начальный и конечный срез для каждой оси тензора

> my_slice = train_images[10:100, :, :]

или

> my_slice = train_images[10:100, 0:28, 0:28]

можно получить срез между любыми двумя индексами по каждой оси тензора
Например, можно выбрать пиксели из области 14 х 14 в правом нижнем углу каждого изображения 

> my_slice = train_images[:, 14:,14:]

можно использовать и отрицательные индексы. Например, обрезать все изображения, оставив только квадрат 14 х 14 пикселов в центре

> my_slice = train_images[:, 7:-7, 7:-7]

Зачастую, первая ось во всех тензорах - это ось образцов

##### 2.2.8. Примеры тензоров с данными

- векторные данные - двумерные тензоры с формой (образцы, признаки)
- временные ряды или последовательности - трехмерные тензоры с формой (образцы, метки_времени, признаки)
- изображения - четырехмерные тензоры с формой (образцы, высота, ширина, цвет) или (образцы, цвет, высота, ширина)
- видео - пятимерные тензоры (образцы, кадры, высота, ширина, цвет) или (образцы, кадры, цвет, высота, ширина)

##### 2.2.9. Векторные данные

Наиболее встречающаяся форма данных. Каждый образец может быть представлен вектором, а пакет двумерным тензором (массивом векторов), где первая ось - ось образов, вторая ось - ось признаков

##### 2.2.10. Временные ряды или последовательности
...

##### 2.2.11. Изображения
Например пакет со 128 черно-белыми изображениями, с размером 256 х 256 можно сохранить в тензоре с формой (128, 256, 256, 1), а пакет с цветными изображениями
в тензоре с формой (128, 256, 256, 3)

В отношении форм тензоров с изображениями  существует два соглашения:
в TensorFlow - канал следует последним
в Theano - канал следует первым
