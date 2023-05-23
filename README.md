//Задача 47. Задайте двумерный массив размером m×n, заполненный случайными вещественными числами от -10,0 до 10,0.
int m = 3; // количество строк
int n = 4; // количество столбцов

Random random = new Random(); // создаем генератор случайных чисел

double[,] array = new double[m, n]; // создаем массив

for (int i = 0; i < m; i++) // проходим по строкам массива
{
    for (int j = 0; j < n; j++) // проходим по столбцам массива
    {
        array[i, j] = random.NextDouble() * 20 - 10; // заполняем ячейки массива случайными числами от -10,0 до 10,0
    }
}

for (int i = 0; i < m; i++) // проходим по строкам массива
{
    for (int j = 0; j < n; j++) // проходим по столбцам массива
    {
        Console.Write(array[i, j] + "\t"); // выводим на консоль значение ячейки массива с разделителем табуляции
    }
    Console.WriteLine(); // переходим на новую строку
}

//Задача 50. Напишите программу, которая на вход принимает число, и возвращает индексы числа в двумерном массиве или же указание, что такого элемента нет.
Console.Write("Введите количество строк в массиве: ");
int m = int.Parse(Console.ReadLine());
Console.Write("Введите количество столбцов в массиве: ");
int n = int.Parse(Console.ReadLine()); 
int[,] array = new int[m, n];
for (int i = 0; i < m; i++) 
{
    for (int j = 0; j < n; j++) 
    {
        Console.Write("Введите элемент массива [{0},{1}]: ", i, j);
        array[i, j] = int.Parse(Console.ReadLine()); 
    }
}

Console.Write("Введите искомый элемент: ");
int target = int.Parse(Console.ReadLine()); 

bool found = false; 
for (int i = 0; i < m; i++) 
{
    for (int j = 0; j < n; j++) 
    {
        if (array[i, j] == target) 
        {
            Console.WriteLine("Искомый элемент найден на позиции [{0}, {1}]", i, j); 
            found = true; 
        }
    }
}

if (!found) 
{
    Console.WriteLine("Указанный элемент отсутствует в массиве"); 
}

//Задача 52. Задайте двумерный массив из целых чисел. Найдите среднее арифметическое элементов в каждом столбце
int[,] array = new int[,] { { 1, 4, 7, 2 }, 
                            { 5, 9, 2, 3 }, 
                            { 8, 4, 2, 4 } }; 

int m = array.GetLength(0);
int n = array.GetLength(1); 

for (int j = 0; j < n; j++) 
{
    int sum = 0; 
    for (int i = 0; i < m; i++) 
    {
        sum += array[i, j]; 
    }
    double average = (double)sum / m; 
    Console.WriteLine("Среднее арифметическое элементов в столбце {0}: {1}", j, average); 
}
