# Тема 7. Работа с файлами (ввод, вывод).
Отчет по Теме #7 выполнил(а):
- Серегеева Кристина Алексеевна 
- ИНО ЗБ ПОАС-22-1

| Задание |  Сам_раб |
| ------ |  ------ |
| Задание 1 | + |
| Задание 2 | + |
| Задание 3 | + | 
| Задание 4 | + | 
| Задание 5 | + |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Самостоятельная работа №1
### Найдите в интернете любую статью (объем статьи не менее 200 слов), 

```python
from collections import Counter
import re

# Чтение данных из файла
with open('article.txt', 'r') as file:
    data = file.read()

# Преобразование текста в список слов
words = re.findall(r'\w+', data.lower())

# Подсчет количества слов
word_count = len(words)

# Определение самого часто встречающегося слова
word_freq = Counter(words)
most_common_word = word_freq.most_common(1)[0][0]

# Вывод результатов
print(f"Количество слов в статье: {word_count}")
print(f"Самое часто встречающееся слово: {most_common_word}")


```
### Результат.
![Меню]().


## Выводы

Все условия задания выполнены!

## Самостоятельная работа №2
### У вас появилась потребность в ведении книги расходов,

```python
def add_expense(date, category, amount):
    with open('expenses.txt', 'a') as file:
        file.write(f"{date},{category},{amount}\n")
    print("Расход успешно добавлен.")


def display_expenses():
    with open('expenses.txt', 'r') as file:
        for line in file:
            print(line.strip())


# Создание файла для хранения расходов, если его нет
open('expenses.txt', 'a').close()

while True:
    print("1. Добавить расход")
    print("2. Вывести все расходы")
    print("3. Выход")

    choice = input("Выберите действие: ")

    if choice == '1':
        date = input("Введите дату расхода: ")
        category = input("Введите категорию расхода: ")
        amount = input("Введите сумму расхода: ")

        add_expense(date, category, amount)

    elif choice == '2':
        print("Существующие расходы:")
        display_expenses()

    elif choice == '3':
        break

```
### Результат.
![Меню]().

## Выводы

Все условия задания выполнены!
  
## Самостоятельная работа №3
### Имеется файл input.txt с текстом на латинице. 

```python
def count_statistics(file_path):
    with open(file_path, 'r') as file:
        text = file.read()

        # Подсчет количества букв латинского алфавита
        letters_count = sum(1 for char in text if char.isalpha() and char.isascii())

        # Подсчет числа слов
        words_count = len(text.split())

        # Подсчет числа строк
        lines_count = text.count('\n') + 1  # Добавляем 1, т.к. последняя строка может быть без \n

        print(f"Input file contains: \n {letters_count} letters,\n {words_count} words, \n {lines_count} lines.")


file_path = 'input.txt'
count_statistics(file_path)

```
### Результат.
![Меню]().

## Выводы

Все условия задания выполнены!
  
## Самостоятельная работа №4
### Напишите программу, которая получает на вход предложение, выводит его в терминал

```python
def censor_sentence(sentence, banned_words):
    censored_sentence = sentence
    for word in banned_words:
        censored_sentence = censored_sentence.replace(word, '*' * len(word))
        censored_sentence = censored_sentence.replace(word.capitalize(), '*' * len(word))
        censored_sentence = censored_sentence.replace(word.upper(), '*' * len(word))
        censored_sentence = censored_sentence.replace(word.lower(), '*' * len(word))
    return censored_sentence

with open('input.txt', 'r') as file:
    banned_words = file.read().split()

input_sentence = input("Введите предложение: ")
censored_output = censor_sentence(input_sentence, banned_words)
print(censored_output)
```
### Результат.
![Меню]().

## Выводы

Все условия задания выполнены!
  
## Самостоятельная работа №5
### Документ «text_for_laba.txt» содержит некоторый текст


```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words = f.read().split()
        max_length = len(max(words, key=len))
        for word in words:
            if len(word) == max_length:
                sought_words = word

        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words
print(longest_words('text_for_laba.txt'))

```
### Результат.
![Меню]().

## Выводы

Все условия задания выполнены!
  


## Общие выводы по теме
Работа с текстовыми файлами в Python предоставляет возможность чтения данных из файла, записи данных в файл, а также обработки содержимого файла. 
