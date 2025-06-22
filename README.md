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

## Задача 1.4  
### Постановка задачи
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

## Задача 2.1  
### Постановка задачи   
Вычислить используя цикл for координаты планеты Марс относительно Земли с течением времени t. Распечатать на экране координаты
для каждой итерации по t. Координаты планеты Марс для каждой
итерации задаются формулами, где r1 – радиус орбиты Марса, r2 – радиус орбиты Земли, T1 и T2 —
периоды обращения указанных планет соответственно, t – каждый
заданный момент времени внутри цикла по времени. Подберите подходящие единицы измерения для времени и расстояния.  
### Математическая модель  
[![image.png](https://i.postimg.cc/yNqktW51/image.png)](https://postimg.cc/JsqrB7Mv)
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| r1  | double  |  радиус орбиты Марса |
| r2  | double  |  радиус орбиты Земли |
| T1  | double  |  период обращения Марса |  
| T2  | double  |  период обращения Земли |  
| t_start  | double  |  начальное время |  
| t_end  | double  |  конечное время |  
| dt  | double  |  шаг |  
| x  | double  |  координата |  
| y  | double  |  координата |  
  
### Код программы
```C
#include <stdio.h>
#include <math.h>

#define PI 3.14159265358979323846

int main() {
	double r1 = 1.524; // в а.е
	double r2 = 1.0;
	double T1 = 1.881; // в годах
	double T2 = 1.0;

	const double w1 = 2 * PI / T1;
	const double w2 = 2 * PI / T2;

	const double t_start = 0.0;
	const double t_end = 5.0;
	const double dt = 0.1; // шаг

	for (double t = t_start; t <= t_end; t += dt) {
		double x = r1 * cos(w1 * t) - r2 * cos(w2 * t);
		double y = r1 * sin(w1 * t) - r2 * sin(w2 * t);
		printf("Time: %.2f\t X:%.6f\t Y:%.6f\n", t, x, y);
	}
	return 0;
}
```  
### Результат выполненной работы:  
[![image.png](https://i.postimg.cc/1XztwFgH/image.png)](https://postimg.cc/2bPrfV7b)

## Задача 2.2  
### Постановка задачи
Вычислить определённый интеграл от заданной функции методом трапеций. Функция f(x) может быть выбрана и самостоятельно. Результат интегрирования сравнить с вычисленным вручную и убедиться в корректности результата.  
Математическая модель:  
[![image.png](https://i.postimg.cc/nrwLkLBt/image.png)](https://postimg.cc/64nw6tMH)
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| a  | double  |  предел интегрирования |
| b  | double  |  предел интегрирования |
| n  | int  |  количество трапеций |  
| integral  | double  |  вычисленное значение |  
| exact  | double  |  значение для проверки |  
| h  | double  |  высота трапеции |  
| sum  | double  |  сумма |  
  
### Код программы:  
```C
#include <stdio.h>
#include <math.h>

double f(double x) {
	return exp(x);
}
double trapezoidal_integral(double a, double b, int n) {
	double h = (b - a) / n;
	double sum = (f(a) + f(b)) / 2.0;

	for (int i = 1; i < n; i++) {
		double x = a + i * h;
		sum += f(x);
	}

	return sum * h;
}

int main() {
	double a = 0.0;
	double b = 1.0;
	int n = 1000; // количество трапеций 

	double integral = trapezoidal_integral(a, b, n);
	double exact = exp(b) - exp(a);

	printf("Calculated integral: %.8f\n", integral);
	printf("Analyzed integral : %.8f\n", exact);
	return 0;
}
```
### Результат выполненной работы:  
[![image.png](https://i.postimg.cc/zDd35xMP/image.png)](https://postimg.cc/3Wv3FF3g)
## Задача 2.3  
### Постановка задачи
Организовать и распечатать последовательность чисел Падована, не
превосходящих число m, введенное с клавиатуры. Числа Падована
представлены следующим рядом: 1, 1, 1, 2, 2, 3, 4, 5, 7, 9,
12, 16, 21, 28, 37, 49, 65, 86, 114, 151, 200, 265, ... Использовать конструкцию for и простые варианты условной конструкции
if else. Для этих чисел заданы формулы.  
### Математическая модель  
[![image.png](https://i.postimg.cc/LsB6WDLD/image.png)](https://postimg.cc/sBxrQpnG)
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| m  | int  |  максимальное число |
| p0  | int  |  первое число |
| p1  | int  |  второе число |  
| p2  | int  |  третье число |  
| current  | int  |  текущее число |  
### Код программы  
```C
#include <stdio.h>
#include <math.h>

int main() {
	int m;
	printf("Enter max number: ");
	scanf("%d", &m);
	int p0 = 1, p1 = 1, p2 = 1;
	int current;
	printf("The sequence of Padovan numbers \n");
	printf("%d ", p0);
	if (m > 1) printf("%d ", p1);
	if (m > 1) printf("%d ", p2);

	// Генерация последующих чисел
	for (int n = 3; ; n++) {
		current = p0 + p1;  // P(n) = P(n-2) + P(n-3)

		if (current > m) break;

		printf("%d ", current);

		// Обновляем предыдущие значения для следующей итерации
		p0 = p1;
		p1 = p2;
		p2 = current;
	}
	printf("\n");
	return 0;
}
```
### Результат выполненной работы  
[![image.png](https://i.postimg.cc/c4g1W0fr/image.png)](https://postimg.cc/QHDZkL43)
## Задача 2.4  
### Постановка задачи
С клавиатуры вводится трёхзначное число, считается сумма его цифр.
Если сумма цифр числа больше 10, то вводится следующее трёхзначное число, если сумма меньше либо равна 10 — программа завершается.  
### Математическая модель  
-
### Список идентификаторов  
| Имя  | Тип | Смысл |
| --- | --- | --- |
| number  | int  |  число |
| sum  | int  |  сумма |
| digit1  | int  |  первая цифра |  
| digit2  | int  |  вторая цифра |  
| digit3  | int  |  третья цифра |  
  
### Код программы  
```C
#include <stdio.h>
#include <math.h>

int main() {
	int number, sum;
	do {
		printf("Enter a three-digit number: ");
		scanf("%d", &number);
		if (number < 100 || number > 999) {
			printf("Number must contain 3 digits\n");
			continue;
		}
		int digit1 = number / 100;
		int digit2 = (number / 10) % 10;
		int digit3 = number % 10;
		sum = digit1 + digit2 + digit3;
		printf("Sum: %d\n", sum);
		if (sum <= 10) {
			printf("Sum <= 10\n");
			break;
		}
	} while (1);
	return 0;
}
```
### Результат выполненной работы  
[![image.png](https://i.postimg.cc/26SmKDzj/image.png)](https://postimg.cc/KKwd1CkC)
