# Тема 9. Концепции и принципы ООП.
Отчет по Теме #9 выполнил(а):
- Сергеева Кристина Алексеевна 
- ИНО ЗБ ПОАС-22-1

| Задание |  Сам_раб |
| ------ |  ------ |
| Задание 1 | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Самостоятельная работа №1
### Задание Садовник и помидоры
## Самостоятельная работа №1
### Задание Садовник и помидоры

```python
class Tomato: #создание класса
    states = {'Семяна': 0, 'Цветение': 1, 'Зреет': 2, 'Спелый': 3}
    def __init__(self, index):  #инициализация объекта
        self._index = index
        self._state = self.states['Семяна']

    def grow(self):  # увеличивает стадию созревания
        if self._state < 3:
            self._state += 1

    def is_ripe(self):
        return True if self._state == 3 else False

class TomatoBush:  #создание класса

    def __init__(self, num):
        self.tomatoes = [Tomato(index) for index in range(1, num + 1)]

    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()

    def all_are_ripe(self): # проверяет помидоры на зрелость
        return all([tomato.is_ripe() for tomato in self.tomatoes])

    def give_away_all(self):
        self.tomatoes = []


class Gardener:  #создание класса

    def __init__(self, name, plant):
        self.name = name
        self._plant = plant

    def work(self):
        self._plant.grow_all()

    def harvest(self): # проверяет, все ли помидоры зрелые
        if self._plant.all_are_ripe():
            print('Урожай собран!')
            self._plant.give_away_all()
        else:
            print('Томаты еще не дозрели')

    @staticmethod
    def knowledge_base():
        print('Справка по садоводству:')
        print('1. Не забывайте регулярно поливать и подкармливать растения')
        print('2. Определите правильное расстояние между растениями, чтобы они не мешали друг другу в росте')
        print('3. Удалите поврежденные листья и плоды, чтобы предотвратить распространение болезней')

    # Вызов справки по садоводству


Gardener.knowledge_base()

# Создание объектов классов TomatoBush и Gardener
bush = TomatoBush(5)
gardener = Gardener('KEVIN', bush)

# Уход за кустом с помидорами
gardener.work()
gardener.work()
gardener.work()


def harvest_tomatoes(unripe=True):
    if unripe:
        print("Попробуйте собрать урожай, когда томаты дозреют")
    else:
        print("Томаты уже спелые, можно начинать сбор урожая")


# Проверка на сбор урожая, когда томаты еще не спелые
harvest_tomatoes(unripe=True)
gardener.harvest()
gardener.work()
gardener.harvest()
gardener.work()

# Сбор урожая после дозревания всех томатов
gardener.work()
gardener.harvest()
```
### Результат.
![Меню](https://github.com/SergeevaKristina21/Software_engineering-/blob/Tema_9/pic_9/1.png)


## Выводы

Все условия задания выполнены!
  


## Общие выводы по теме
Классы являются основным строительным блоком объектно-ориентированного программирования в Python. Они позволяют создавать объекты, которые являются экземплярами класса, и определять, как эти объекты будут работать и взаимодействовать. 












