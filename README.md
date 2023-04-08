# **Итоговая проверочная работа**

## **Условия задачи**


1. Создать репозиторий на **GitHub**
2. Нарисовать блок-схему алгоритма (*можно обойтись блок-схемой основной содержательной части, если вы выделяете её в отдельный метод*)
3. Снабдить репозиторий оформленным текстовым описанием решения (*файл **README.md***)
4. Написать программу, решающую поставленную задачу
5. Использовать контроль версий в работе над этим небольшим проектом (не должно быть так, что всё залито одним коммитом, как минимум этапы 2, 3, и 4 должны быть расположены в разных коммитах)

**Задача:**

Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

**Примеры:**


>[“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]  
[“1234”, “1567”, “-2”, “computer science”] → [“-2”]  
[“Russia”, “Denmark”, “Kazan”] → []

***

# **Решение**

1. Вы находитесь в созданном репозитории Final_test_work.
2. Блок-схема алгоритма:

<kbd><img src="https://github.com/TatyanaProtas/Final_test_work/blob/main/блок_схема.png?raw=true"/></kbd>

3. Вы читаете данный файл README.md

4. Программа находится в ветке [master](https://github.com/TatyanaProtas/Final_test_work/blob/main/Final_test-work.cs "перейти у решению")

Код программы:

```
Commands();
string[] array = new string[] {};

string fromUser = ReadInput("Введите команду: ");
switch (fromUser)
{
    case "1":
        array = new string[] { "Hello", "2", "world", ":-)" };
        break;
    case "2":
        array = new string[] { "1234", "1567", "-2", "computer science" };
        break;
    case "3":
        array = new string[] { "Russia", "Denmark", "Kazan" };
        break;
    default:
        Console.WriteLine($"{fromUser} - Такой команды нет");
        break;
}


int lenNewArray = 0;
for (int i = 0; i <= array.Length - 1; i++)
{
    if (array[i].Length <= 3) lenNewArray++;
}

string[] newArray = new string[lenNewArray];
int idx = 0;

for (int i = 0; i <= array.Length - 1; i++)
{
    if (array[i].Length <= 3)
    {
        newArray[idx] = array[i];
        idx++;
    }
}

PrintArray(array);
Console.Write("→ ");
PrintArray(newArray);

void Commands()
{
    Console.WriteLine();
    Console.WriteLine("СПИСОК КОМАНД:");
    Console.WriteLine("1 – использовать массив: [“Hello”, “2”, “world”, “:-)”]");
    Console.WriteLine("2 – использовать массив: [“1234”, “1567”, “-2”, “computer science”]");
    Console.WriteLine("3 – использовать массив: [“Russia”, “Denmark”, “Kazan”]");
    Console.WriteLine();
}

string ReadInput(string msg)
{
    Console.Write(msg);
    return Console.ReadLine();
}

void PrintArray(string[] array)
{
    Console.Write("[ ");
    for (int i = 0; i < array.Length; i++)
    {
        Console.Write($"“{array[i]}”, ");
    }
    Console.Write("] ");
}
```
Результат ввода в терминал


<kbd><img src="https://github.com/TatyanaProtas/Final_test_work/blob/main/задача_решена1.png?raw=true"/></kbd>

5. Скриншот коммитов

<kbd><img src="https://github.com/TatyanaProtas/Final_test_work/blob/main/Screenshot.png?raw=true"/></kbd>