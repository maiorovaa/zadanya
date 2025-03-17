задание 1. 
/*using System;

class Program
{
    static void Main()
    {
        // Запрос суммы вклада у пользователя
        Console.Write("Введите сумму вклада: ");
        decimal depositAmount = Convert.ToDecimal(Console.ReadLine());

        // Запрос количества месяцев у пользователя
        Console.Write("Введите количество месяцев: ");
        int months = Convert.ToInt32(Console.ReadLine());

        // Процентная ставка
        decimal interestRate = 0.07m;

        // Вычисление конечной суммы вклада
        for (int i = 0; i < months; i++)
        {
            depositAmount += depositAmount * interestRate;
        }

        // Вывод конечной суммы
        Console.WriteLine($"Конечная сумма вклада: {depositAmount:F2}");
    }
}
*/
/*
Задание 2
using System;

class Program
{
    static void Main()
    {
        // Запрос суммы вклада у пользователя
        Console.Write("Введите сумму вклада: ");
        decimal depositAmount = Convert.ToDecimal(Console.ReadLine());

        // Запрос количества месяцев у пользователя
        Console.Write("Введите количество месяцев: ");
        int months = Convert.ToInt32(Console.ReadLine());

        // Процентная ставка
        decimal interestRate = 0.07m;

        // Инициализация счетчика месяцев
        int monthCounter = 0;

        // Вычисление конечной суммы вклада с использованием цикла while
        while (monthCounter < months)
        {
            depositAmount += depositAmount * interestRate;
            monthCounter++;
        }

        // Вывод конечной суммы
        Console.WriteLine($"Конечная сумма вклада: {depositAmount:F2}");
    }
}
*/
/*
задание 3
using System;

class Program
{
    static void Main()
    {
        // Заголовок таблицы
        Console.WriteLine("Таблица умножения:");
        
        // Внешний цикл для чисел от 1 до 10
        for (int i = 1; i <= 10; i++)
        {
            // Внутренний цикл для умножения
            for (int j = 1; j <= 10; j++)
            {
                // Вывод результата умножения
                Console.Write($"{i * j,4}"); // Форматирование для выравнивания
            }
            // Переход на новую строку после каждой строки таблицы
            Console.WriteLine();
        }
    }
}
*/
/*
задание 4
using System;

class Program
{
    static void Main()
    {
        while (true) // Бесконечный цикл
        {
            Console.Write("Введите первое число (от 0 до 10): ");
            string input1 = Console.ReadLine();
            Console.Write("Введите второе число (от 0 до 10): ");
            string input2 = Console.ReadLine();

            // Попытка преобразовать введенные строки в числа
            if (int.TryParse(input1, out int number1) && int.TryParse(input2, out int number2))
            {
                // Проверка диапазона
                if (number1 >= 0 && number1 <= 10 && number2 >= 0 && number2 <= 10)
                {
                    // Вывод результата умножения
                    int result = number1 * number2;
                    Console.WriteLine($"Результат умножения {number1} * {number2} = {result}");
                    break; // Выход из цикла, если числа корректные
                }
                else
                {
                    Console.WriteLine("Недопустимые числа. Пожалуйста, введите числа от 0 до 10.");
                }
            }
            else
            {
                Console.WriteLine("Ошибка ввода. Пожалуйста, введите целые числа.");
            }
        }
    }
}
Теоретические вопросы
Вопрос 1
Сколько элементов имеет следующий массив?
1
int[,,] numbers = new int[3, 2, 3];
ответ: 6) 18
Вопрос 2
Сколько измерений (размерность) имеет следующий массив?
1
int[,] numbers = new int[3, 3];
ответ:2) 2
Вопрос 3
Что будет выведено на консоль в результате выполнения следующего кода:
1. int[][] nums = new int[3][];
2. nums[0] = new int[2] { 1, 2 };
3. nums[1] = new int[3] { 3, 4, 5 }; 
4. nums[2] = new int[5] { 6, 7, 8, 9, 10 };
5. Console.WriteLine(nums[3][2]);
Ответ: 1.null
2. { 1, 2 }
3. { 3, 4, 5}
4. { 6, 7, 8, 9, 10}
5. попытка обращения к nums[3] приводит к исключению IndexOutOfRangeException, так как индекс выходит за пределы доступных значений массива.
Вопрос 4
Дан следующий массив
1
2
3
4
int[][] nums = new int[3][];
nums[0] = new int[2] { 1, 2 };
nums[1] = new int[3] { 3, 4, 5 }; 
nums[2] = new int[5] { 6, 7, 8, 9, 10 };
Каким образом мы можем обратиться к числу 7 в этом массиве?
ответ: 3) nums[2][1]
Практические вопросы
Упражнение 1
using System;

class Program
{
    static void Main()
    {
        int[,,] mas = { 
            { { 1, 2 }, { 3, 4 } }, 
            { { 4, 5 }, { 6, 7 } }, 
            { { 7, 8 }, { 9, 10 } }, 
            { { 10, 11 }, { 12, 13 } } 
        };

        Console.Write("{{{");
        
        for (int i = 0; i < mas.GetLength(0); i++)
        {
            for (int j = 0; j < mas.GetLength(1); j++)
            {
                Console.Write("{");
                for (int k = 0; k < mas.GetLength(2); k++)
                {
                    Console.Write(mas[i, j, k]);
                    if (k < mas.GetLength(2) - 1)
                    {
                        Console.Write(", ");
                    }
                }
                Console.Write("}");
                if (j < mas.GetLength(1) - 1)
                {
                    Console.Write(", ");
                }
            }
            Console.Write("}");
            if (i < mas.GetLength(0) - 1)
            {
                Console.Write(", ");
            }
        }

        Console.Write("}}}");
    }
}
