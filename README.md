# Программирование. Язык СИ. Математические операции. Переменные и их типы. Операторы. Циклы. Простые условные конструкции. Основы работы со статическими массивами.
## Задача 1.2
### Постановка задачи
Написать простую программу.Ввести два числа с клавиатуры, вычислить их сумму и напечатать результат. Использовать функцию printf для приглашений на ввод и для распечатки результата. Использовать функцию scanf для ввода каждого числа отдельно с клавиатуры. Для получения доступа к функциям printf и scanf включить в программу заголовочный файл stdio.h. Использовать корректные спецификаторы форматирования. Здесь и далее для распечатки надписей на экране использовать латинские буквы для избежания проблем с кодировками символов.
### Математическая модель
-
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| a  | int  |  Первое число |
| b  | int  |  Второе число |
| s  | int  |  Сумма чисел |  

### Код программы
```C
#include <stdio.h>

int main() {
	int a, b, s;

	printf("Enter number 1: ");
	scanf("%d", &a);

	while (getchar() != '\n');

	printf("Enter number 2: ");
	scanf("%d", &b);

	s = a + b;
	printf("Sum = %d\n", s);
	return 0;
}
```
### Результат выполненной работы  
[![image.png](https://i.postimg.cc/d0n44MH9/image.png)](https://postimg.cc/LqYt8WMq)

## Задача 1.3  
### Постановка задачи  
Вычислить значение выражения
### Математическая модель
[![image.png](https://i.postimg.cc/w3KV79M9/image.png)](https://postimg.cc/Pv4Z7s17)

### Информация о студенте  
Иванишин Даниил Евгеньевич, 1 курс, ИВТ-1.1  
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| x  | double  |  Первое число |
| y  | double  |  Второе число |
| u  | double  |  Результат    |  
  
### Код программы
```C
#include <stdio.h>
#include <math.h>

int main() {
	double x, y, u;
	printf("Enter x: ");
	scanf("%lf", &x);
	printf("Enter y: ");
	scanf("%lf", &y);

	u = (1 + pow(sin(x + y), 2)) / (2 + fabs(x - (2 * pow(x, 2)) / (1 + fabs(sin(x + y)))));

	printf("u(%.2f, %.2f) = %.6f\n", x, y, u);
	return 0;
}
```
### Результат выполненной работы  
[![image.png](https://i.postimg.cc/4NCqKgrK/image.png)](https://postimg.cc/RqRX8jC9)

## 1.4  
### Задача  
Вычислить значение выражения и выполнить для следующих значений:  
a = 0.12, b = 3.5, c = 2.4, x = 1.4 ;  
a = 0.12, b = 3.5, c = 2.4, x = 1.6 ;  
a = 0.27, b = 3.9, c = 2.8, x = 1.8 .  
Значения параметров и аргументов можно вводить прямо в коде программы без ввода с клавиатуры.
### Математическая модель  
[![image.png](https://i.postimg.cc/xTSpfPzM/image.png)](https://postimg.cc/pyqJkzkL)
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| a  | double  |  переменная для вычисления формулы |
| b  | double  |  переменная для вычисления формулы |
| c  | double  |  переменная для вычисления формулы |  
| x  | double  |  переменная для вычисления формулы |  
| term1  | double  |  первое слагаемое |  
| numerator  | double  |  числитель второго слагаемого |  
| denominator  | double  |  делитель второго слагаемого |  
| term2  | double  |  второе слагаемое |  
  
### Код программы
```C
#include <stdio.h>
#include <math.h>

double calculate_h(double x, double a, double b, double c) {
	double term1 = -(x - a) / cbrt(x * x + a * a);

	double numerator = 4 * pow(pow(x * x + b * b, 3), 0.25);
	double denominator = 2 + a + b + cbrt(pow(x - c, 2));
	double term2 = numerator / denominator;

	return term1 - term2;
}

int main() {
	double a = 0.12, b = 3.5, c = 2.4, x = 1.4;
	printf("1. %lf \n", calculate_h(x, a, b, c));
	a = 0.12, b = 3.5, c = 2.4, x = 1.6;
	printf("2. %lf \n", calculate_h(x, a, b, c));
	a = 0.27, b = 3.9, c = 2.8, x = 1.8;
	printf("3. %lf \n", calculate_h(x, a, b, c));
	return 0;
}
```  
### Результат выполненной работы  
[![image.png](https://i.postimg.cc/SxxrR1N2/image.png)](https://postimg.cc/mtKM6w9B)
