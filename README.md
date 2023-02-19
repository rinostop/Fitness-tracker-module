# Модуль фитнес-трекера

Этот модуль предоставляет классы и функции для отслеживания фитнес-тренировок различных типов, таких как бег, ходьба и плавание.

### Модуль состоит из следующих классов:
- "InfoMessage": информационное сообщение о тренировке с методами получения различных параметров тренировки.
- "Training": базовый класс для всех типов тренировок. Он предоставляет методы для получения расстояния, средней скорости и потраченных калорий.
- "Running": класс для отслеживания беговых тренировок. Он наследуется от класса Training и предоставляет метод для подсчета потраченных калорий.
- "SportsWalking": класс для отслеживания тренировок по спортивной ходьбе. Он наследуется от класса "Training" и предоставляет метод для подсчета потраченных калорий.
- "Swimming": класс для отслеживания тренировок по плаванию. Он наследуется от класса "Training" и предоставляет методы для получения расстояния, средней скорости и потраченных калорий.

Кроме того, модуль выполняет две функции:
- "read_package": функция для считывания данных, полученных от датчиков, и создания объекта "Training" на основе типа тренировки.
- "main": функция для печати информации о тренировке с использованием класса "InfoMessage".

### Как использовать:
Чтобы использовать модуль, вы можете импортировать необходимые вам классы и функции.
Вот пример использования модуля для отслеживания тренировок:

```python
from fitness_tracker import read_package, main

packages = [
    ('SWM', [720, 1, 80, 25, 40]),
    ('RUN', [15000, 1, 75]),
    ('WLK', [9000, 1, 75, 180]),
]

for workout_type, data in packages:
    training = read_package(workout_type, data)
    main(training)
```
Это позволит распечатать информацию о тренировке в следующем формате:
```python
Тип тренировки: Swimming;
Длительность: 1.000 ч.;
Дистанция: 1.125 км;
Ср. скорость: 1.125 км/ч;
Потрачено ккал: 99.000.

Тип тренировки: Running;
Длительность: 1.000 ч.;
Дистанция: 9.750 км;
Ср. скорость: 9.750 км/ч;
Потрачено ккал: 1093.875.

Тип тренировки: SportsWalking;
Длительность: 1.000 ч.;
Дистанция: 5.850 км;
Ср. скорость: 5.850 км/ч;
Потрачено ккал: 346.500.
```
#### Еще один пример:
```python
from fitness_tracker import Running

duration = 1.5  # in hours
distance = 10.0  # in kilometers
weight = 70.0  # in kilograms

running = Running(distance, duration, weight)
calories = running.get_spent_calories()

print(f"Calories burned: {calories:.2f}")
```
В этом примере мы создаем объект "Running" с заданными расстоянием, продолжительностью и весом. Затем мы вызываем метод "get_spent_calories()", чтобы вычислить количество калорий, сожженных во время тренировки.

### Требования
Для работы модуля требуется Python 3.7 или выше и модуль dataclasses. Чтобы установить модуль и его зависимости, используйте следующую команду:
```python
pip install fitness-tracker
```
