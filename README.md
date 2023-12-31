# Тема 6. Базовые коллекции: словари, кортежи
Отчет по Теме #6 выполнил(а):
- Легков Иван Сергеевич
- ПИЭ-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 |  | |
| Задание 7 |  | |
| Задание 8 |  |  |
| Задание 9 |  |  |
| Задание 10 |  |  |

# Лабараторные работы 
   ## Лабараторная работа 1
В школе, где вы учились, узнали, что вы крутой программист и попросили написать программу для учителей, которая будет при вводе кабинета писать для него ключ доступа и статус, занят кабинет или нет. При написании программы необходимо использовать словарь (dict), который на вход получает номер кабинета, а выводит необходимую информацию. Если кабинета, который вы ввели нет в словаре, то в консоль в в в виде значения ключа нужно вывести “None” и виде статуса вывести “False”. По большому счету написав данную программу мы с вами научились заменять иногда громоздкую конструкцию if/elif/else. Поскольку здесь функционал словаря полностью повторяет функционал условия, но при этом у использования словарей в более сложных программах есть намного больше возможностей реализации

  ```python
request = int(input("Введите номер кабинета:"))
dictionary = {
    101:{"key": 1234, 'access':True},
    102: {"key": 1337, 'access': True},
    103: {"key": 8943, 'access': True},
    104: {"key": 5555, 'access': False},
    None: {"key": None, 'access': False},

}

response = dictionary.get(request)
if not response:
    response = dictionary[None]
key = response.get('key')
access = response.get('acces')
print(key,access)

```
  ### Результат
  ![1](https://github.com/armuane/laba6/blob/main/1.png?raw=true)

 
## Краткий вывод:
request = int(input("Введите номер кабинета:")): Программа запрашивает у пользователя ввод номера кабинета и преобразует введенное значение в целое число.

dictionary: Создается словарь dictionary, в котором ключами являются номера кабинетов, а значениями являются вложенные словари с информацией о ключе и доступе.

response = dictionary.get(request): Пытается получить значение из словаря по введенному номеру кабинета. Если номер кабинета не найден, response будет равен None.

if not response:: Проверяет, было ли найдено значение для введенного номера кабинета. Если значение не было найдено (т.е., response равно None), то присваивается значение для случая, когда номер кабинета не указан явно (None).

key = response.get('key'): Получает значение ключа 'key' из вложенного словаря response.

access = response.get('acces'): Попытка получить значение ключа 'acces' из вложенного словаря response. Однако, в словаре ключ называется 'access', а не 'acces', поэтому будет возвращено значение None.

print(key, access): Выводит значения key и access в консоль.


   ## Лабараторная работа 2
Алексей решил создать самый большой словарь в мире. Для этого он придумал функцию dict_maker (**kwargs), которая принимает неограниченное количество параметров «ключ: значение» и обновляет Михаил А. Панов созданный им словарь my_dict, состоящий всего из одного элемента «first» со значением «so easy». Помогите Алексею создать данную функцию. Ниже на скриншоте мы использовали встроенный модуль pprint который выводит большие объемы информации более понятно для восприятия человеческим глазом. Иногда очень удобно использовать данную возможность Python.

  ```python
from pprint import pprint

my_dict = {'first ': 'so easy'}

def dict_maker(**kwargs):
    my_dict.update(**kwargs)

dict_maker(a1=1, a2=20, a3=54, a4=13)
dict_maker(name='Михаил',age=31,weight=70,eyes_color="blue")
pprint(my_dict)

```
  ### Результат
  ![2](https://github.com/armuane/laba6/blob/main/2.png?raw=true)

 
## Краткий вывод:
from pprint import pprint: Импортируется функция pprint из модуля pprint. Эта функция используется для красивого вывода сложных структур данных, таких как словари.

my_dict = {'first ': 'so easy'}: Создается словарь my_dict с одним элементом, ключом "first " и значением "so easy".

def dict_maker(**kwargs):: Определена функция dict_maker, которая принимает произвольное количество именованных аргументов (**kwargs).

my_dict.update(**kwargs): Внутри функции используется метод update для обновления словаря my_dict значениями из переданных аргументов.

dict_maker(a1=1, a2=20, a3=54, a4=13): Функция вызывается с аргументами a1=1, a2=20, a3=54, a4=13. Она обновляет my_dict этими значениями.

dict_maker(name='Михаил', age=31, weight=70, eyes_color="blue"): Еще один вызов функции с новыми аргументами, которые также обновляют my_dict.

pprint(my_dict): Выводится содержимое словаря my_dict с использованием функции pprint.


   ## Лабараторная работа 3
Для решения некоторых задач бывает необходимо разложить строку на отдельные символы. Мы знаем что это можно сделать при помощи split(), у которого более гибкая настройка для разделения для этого, но если нам нужно посимвольно разделить строку без всяких условий, то для этого мы можем использовать кортежи (tuple). Для этого напишем любую строку, которую будем делить и “обвернем” ее в tuple и дальше как с кортежом

  ```python
input_string ='HelloWorld'
result = tuple(input_string)
print(result)
print(list(result))

```
  ### Результат
  ![3](https://github.com/armuane/laba6/blob/main/3.png?raw=true)

 
## Краткий вывод:

input_string = 'HelloWorld': Создается строковая переменная input_string со значением 'HelloWorld'.

result = tuple(input_string): Функция tuple() используется для преобразования строки input_string в кортеж (tuple). Каждый символ строки становится элементом кортежа. Таким образом, переменная result будет кортежем, содержащим отдельные символы из строки.

print(result): Выводится кортеж result. Каждый символ строки разделен запятой внутри кортежа.

print(list(result)): Функция list() используется для преобразования кортежа result обратно в список. Затем этот список выводится. Результат будет таким же, как если бы каждый символ строки был элементом списка.

   ## Лабараторная работа 4
Вовочка решил написать крутую функцию, которая будет писать имя, возраст и место работы, но при этом на вход этой функции будет поступать кортеж. Помогите Вовочке написать эту программу

  ```python
def personal_info(name,age,company ="unnamed"):
    print(f'Имя:{name} Возраст:{age} Компания:{company}')
tom = ("Григории",22)
personal_info(*tom)
bob =("Георгий",41,"Yandex")
personal_info(*bob)
```
  ### Результат
  ![4](https://github.com/armuane/laba6/blob/main/4.png?raw=true)

 
## Краткий вывод:
В данном коде определена функция personal_info, которая принимает три параметра: name, age и company (последний имеет значение по умолчанию "unnamed"). Функция выводит информацию о человеке, включая имя, возраст и компанию, если она указана.


   ## Лабараторная работа 5
Для сопровождения первых лиц государства X нужен кортеж, но никто не может определиться с порядком машин, поэтому вам нужно написать функцию, которая будет сортировать кортеж, состоящий из целых чисел по возрастанию, и возвращает его. Если хотя бы один элемент не является целым числом, то функция возвращает исходный кортеж

  ```python
def tuple_sort(tpl):
    for elm in tpl:
        if not isinstance(elm,int):
            return tpl
    return tuple(sorted(tpl))

if __name__ == '__main__':
    print(tuple_sort((5,5,3,1,9)))
    print(tuple_sort((5, 5, 2.1, "1", 9)))
```
  ### Результат
  ![5](https://github.com/armuane/laba6/blob/main/5.png?raw=true)

 
## Краткий вывод:
Проходит по каждому элементу кортежа (elm) с помощью цикла for.

Проверяет, является ли каждый элемент целым числом (int). Если хоть один элемент не является целым числом, то возвращается исходный кортеж без изменений.

Если все элементы являются целыми числами, то функция создает новый кортеж, который получен из отсортированной версии исходного кортежа, используя функцию sorted.

Возвращается новый отсортированный кортеж.

Затем, в блоке if __name__ == '__main__': выполняются два примера вызова функции tuple_sort:

tuple_sort((5,5,3,1,9)): Все элементы этого кортежа являются целыми числами, поэтому функция вернет отсортированный кортеж (1, 3, 5, 5, 9).

tuple_sort((5, 5, 2.1, "1", 9)): Этот кортеж содержит элементы разных типов (целое число, число с плавающей запятой, строка). Поскольку есть элементы, не являющиеся целыми числами, функция вернет исходный кортеж без изменений.





# Самостоятельные работы
   ## Самотоятельная работа 1
При создании сайта у вас возникла потребность обрабатывать данные пользователя в странной форме, а потом переводить их в нужные вам форматы. Вы хотите принимать от пользователя последовательность чисел, разделенных пробелом, а после переформатировать эти данные в список и кортеж. Реализуйте вашу задумку. Для получения начальных данных используйте input(). Результатом программы будет выведенный список и кортеж из начальных данных

  ```python
def process_user_data(data_str):
    # Разделение строки на числа и создание списка
    num_list = [int(num) for num in data_str.split()]

    # Создание кортежа из списка
    num_tuple = tuple(num_list)

    return num_list, num_tuple

# Получение данных от пользователя
user_input = input("Введите последовательность чисел, разделенных пробелом: ")

# Обработка данных и вывод результатов
result_list, result_tuple = process_user_data(user_input)

# Вывод списка и кортежа
print("Список:", result_list)
print("Кортеж:", result_tuple)
```
  ### Результат
  ![6](https://github.com/armuane/laba6/blob/main/6.png?raw=true)

  
 
## Краткий вывод:
Программа сначала запрашивает у пользователя ввод последовательности чисел, разделенных пробелом. Затем она обрабатывает эту строку, создавая из нее список и кортеж, используя функцию process_user_data. Наконец, программа выводит полученные список и кортеж.

  ## Самотоятельная работа 2
Николай знает, что кортежи являются неизменяемыми, но он очень упрямый и всегда хочет доказать, что он прав. Студент решил создать функцию, которая будет удалять первое появление определенного элемента из кортежа по значению и возвращать кортеж без него. Попробуйте повторить шедевр не признающего авторитеты начинающего программиста. Но учтите, что Николай не всегда уверен в наличии элемента в кортеже (в этом случае кортеж вернется функцией в исходном виде). Входные данные: (1, 2, 3), 1) (1, 2, 3, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2), 3) (2, 4, 6, 6, 4, 2), 9) Ожидаемый результат: (2, 3) (1, 2, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2) (2, 4, 6, 6, 4, 2)

  ```python
def remove_element_from_tuple(tpl, element):
    # Проверяем, присутствует ли элемент в кортеже
    if element in tpl:
        # Находим индекс первого вхождения элемента
        index = tpl.index(element)
        # Создаем новый кортеж без первого вхождения элемента
        new_tpl = tpl[:index] + tpl[index + 1:]
        return new_tpl
    else:
        # Если элемента нет, возвращаем исходный кортеж
        return tpl

# Примеры использования
tuple1 = (1, 2, 3)
result1 = remove_element_from_tuple(tuple1, 1)
print(result1)  # Ожидаемый результат: (2, 3)

tuple2 = (1, 2, 3, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2)
result2 = remove_element_from_tuple(tuple2, 3)
print(result2)  # Ожидаемый результат: (1, 2, 1, 2, 3, 4, 5, 2, 3, 4, 2, 4, 2)

tuple3 = (2, 4, 6, 6, 4, 2)
result3 = remove_element_from_tuple(tuple3, 9)
print(result3)  # Ожидаемый результат: (2, 4, 6, 6, 4, 2)
```
  ### Результат
  ![7](https://github.com/armuane/laba6/blob/main/7.png?raw=true)

 
## Краткий вывод:
Таким образом, если элемент присутствует в кортеже, функция удаляет его первое вхождение и возвращает новый кортеж. Если элемента нет, возвращается исходный кортеж.
  ## Самотоятельная работа 3
Ребята поспорили кто из них одним нажатием на numpad наберет больше повторяющихся цифр, но не понимают, как узнать победителя. Вам им нужно в этом помочь. Дана строка в виде случайной последовательности чисел от 0 до 9 (длина строки минимум 15 символов). Требуется создать словарь, который в качестве ключей будет принимать данные числа (т. е. ключи будут типом int), а в качестве значений – количество этих чисел в имеющейся последовательности. Для построения словаря создайте функцию, принимающую строку из цифр. Функция должна возвратить словарь из 3-х самых часто встречаемых чисел, также эти значения нужно вывести в порядке возрастания ключа

  ```python
def count_most_common_digits(numbers_str):
    # Подсчитываем количество вхождений каждой цифры в строке
    digit_counts = {}
    for digit in numbers_str:
        digit = int(digit)
        digit_counts[digit] = digit_counts.get(digit, 0) + 1

    # Сортируем цифры по количеству вхождений в убывающем порядке
    sorted_digits = sorted(digit_counts, key=digit_counts.get, reverse=True)

    # Создаем словарь из 3 самых часто встречаемых цифр
    result_dict = {digit: digit_counts[digit] for digit in sorted_digits[:3]}

    return result_dict

# Пример использования
numbers_string = "45678901234567890"
result_dictionary = count_most_common_digits(numbers_string)

# Выводим результат
print(result_dictionary)
```
  ### Результат
  ![8](https://github.com/armuane/laba6/blob/main/8.png?raw=true)

 
## Краткий вывод:

В этом коде функция count_most_common_digits принимает строку чисел, подсчитывает количество вхождений каждой цифры и создает словарь, содержащий три самые часто встречаемых цифры в порядке возрастания ключа.

  ## Самотоятельная работа 4
Ваш хороший друг владеет офисом со входом по электронным картам, ему нужно чтобы вы написали программу, которая показывала в каком порядке сотрудники входили и выходили из офиса. Определение сотрудника происходит по id. Напишите функцию, которая на вход принимает кортеж и случайный элемент (id), его можно придумать самостоятельно. Требуется вернуть новый кортеж, начинающийся с первого появления элемента в нем и заканчивающийся вторым его появлением включительно. Если элемента нет вовсе – вернуть пустой кортеж. Если элемент встречается только один раз, то вернуть кортеж, который начинается с него и идет до конца исходного. Входные данные: (1, 2, 3), 8) (1, 8, 3, 4, 8, 8, 9, 2), 8) (1, 2, 8, 5, 1, 2, 9), 8) Ожидаемый результат: () (8, 3, 4, 8) (8, 5, 1, 2, 9) 5) 

  ```python
def extract_employee_data(data, employee_id):
    start_index = -1
    end_index = -1
    found_count = 0

    for i, item in enumerate(data):
        if item == employee_id:
            if found_count == 0:
                start_index = i
            found_count += 1
            end_index = i

    if found_count == 0:
        return ()
    elif found_count == 1:
        return data[start_index:]
    else:
        return data[start_index:end_index + 1]

# Примеры использования
data1 = (1, 2, 3)
result1 = extract_employee_data(data1, 8)
print(result1)  # Ожидаемый результат: ()

data2 = (1, 8, 3, 4, 8, 8, 9, 2)
result2 = extract_employee_data(data2, 8)
print(result2)  # Ожидаемый результат: (8, 3, 4, 8)

data3 = (1, 2, 8, 5, 1, 2, 9)
result3 = extract_employee_data(data3, 8)
print(result3)  # Ожидаемый результат: (8, 5, 1, 2, 9)

```
  ### Результат
  ![9](https://github.com/armuane/laba6/blob/main/9.png?raw=true)

 
## Краткий вывод:
Функция extract_employee_data принимает кортеж data и элемент employee_id. Она находит первое и последнее вхождение employee_id в кортеже и возвращает подкортеж, начиная с первого вхождения и заканчивая вторым включительно. Если элемент не встречается, возвращается пустой кортеж. Если элемент встречается только один раз, возвращается кортеж, начиная с этого элемента и до конца исходного кортежа.

  ## Самотоятельная работа 5
Написать функцию, которая принимает список чисел, а затем возвращает кортеж, содержащий сумму и произведение этих чисел.

  ```python
def calculate_sum_and_product(numbers):
    if not numbers:
        return None  # Если список пустой, возвращаем None

    sum_result = sum(numbers)
    product_result = 1
    for num in numbers:
        product_result *= num

    return sum_result, product_result

# Тесты
test1 = [1, 2, 3, 4, 5]
result1 = calculate_sum_and_product(test1)
print(result1)  # Ожидаемый результат: (15, 120)

test2 = [2, 3, 5, 7]
result2 = calculate_sum_and_product(test2)
print(result2)  # Ожидаемый результат: (17, 210)

test3 = []
result3 = calculate_sum_and_product(test3)
print(result3)  # Ожидаемый результат: None

```
  ### Результат
  ![10](https://github.com/armuane/laba6/blob/main/10.png?raw=true)

 
## Краткий вывод:
В данной задаче используется список numbers, а результатом функции является кортеж, содержащий сумму и произведение элементов списка. В тестах проверяется корректность работы функции для различных входных данных, включая пустой список.
# Общий вывод:
Оба типа коллекций могут использоваться для эффективного хранения и организации данных.
Словари поддерживают динамическое добавление и удаление элементов, что делает их удобными для работы с изменяемыми данными.
Кортежи являются неизменяемыми, что обеспечивает стабильность данных и защиту от случайных изменений.
Использование словарей и кортежей в зависимости от контекста может значительно улучшить читаемость и производительность кода.
