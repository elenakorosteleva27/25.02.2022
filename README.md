# 25.02.2022
Задача 1. 
Даны четыре действительных числа: x1, y1, x2, y2. Напишите функцию distance(x1, y1, x2, y2), вычисляющую расстояние между точкой (x1,y1) и (x2,y2). Считайте четыре действительных числа и выведите результат работы этой функции.
from math import sqrt
 
def distance(x1, y1, x2, y2):
    return sqrt((x1 - x2) ** 2 + (y1 - y2) ** 2)
 
x1 = float(input())
x2 = float(input())
y1 = float(input())
y2 = float(input())
print(distance(x1, x2, y1, y2))
Задача 2.
Напишите функцию min4(a, b, c, d), вычисляющую минимум четырех чисел, которая не содержит инструкции if, а использует стандартную функцию min. Считайте четыре целых числа и выведите их минимум.
a = int(input())
b = int(input())
c = int(input())
d = int(input())
 
 
def min4(a, b, c, d):
    return min(min(min(a, b), c), d)
 
 
print(min4(a, b, c, d))
Задача 3.
Даны два действительных числа x и y. Проверьте, принадлежит ли точка с координатами (x,y) заштрихованному квадрату (включая его границу). Если точка принадлежит квадрату, выведите слово YES, иначе выведите слово NO. На рисунке сетка проведена с шагом 1.
>>> start = 1
>>> end = -1
>>> 
>>> def IsPointInSquare(x, y):
...   return (x<=start and x>=end) and (y>=end and y<=start)
... 
>>> if IsPointInSquare(2,0):
...   print 'YES'
... else:
...   print 'NO'
... 
NO
>>> if IsPointInSquare(1,1): 
...     print 'YES'
...     
... else:
...     print 'NO'
...     
... 
YES
Задача 4.
Даны два действительных числа x и y. Проверьте, принадлежит ли точка с координатами (x,y) заштрихованному квадрату (включая его границу). Если точка принадлежит квадрату, выведите слово YES, иначе выведите слово NO. На рисунке сетка проведена с шагом 1.
def ipis(x,y):
      if abs(x)<=1 and abs(y)<=1:
            return True
      else:
            return False
 
 
def IsPointInSquare(x,y):
      return ipis(x,y)
Задача 5. 
Даны пять действительных чисел: x, y, xc, yc, r. Проверьте, принадлежит ли точка (x,y) кругу с центром (xc,yc) и радиусом r. Если точка принадлежит кругу, выведите слово YES, иначе выведите слово NO.
def func(x,y,xc,yc,r):
    return (x - xc) * (x - xc) + (y - yc) * (y - yc) <= r * r
 
if __name__ == '__main__':
    x=float(input())
    y=float(input())
    xc=float(input())
    yc=float(input())
    r=float(input())
    func(x,y,xc,yc,r)
    if func(x, y, xc, yc, r):
        print("YES")
    else:
        print("NO")
Задача 6. 
Если точка принадлежит области (область включает границы), выведите слово YES, иначе выведите слово NO.
def IsPointInCircle(x, y):
    return (x + 1) * (x + 1) + (y - 1) * (y - 1) <= 4
def IsPointInsideCircle(x, y):
    return (x + 1) * (x + 1) + (y - 1) * (y - 1) < 4
def IsPointInArea(x, y):
    llr = (x + y >= 0)
    rll = (2 * x - y + 2 <= 0)
    lll = (x + y <= 0)
    rlr = (2 * x - y + 2 >= 0)
    in1 = IsPointInCircle(x, y) and llr and rll
    in2 = not(IsPointInsideCircle(x, y)) and lll and rlr
    return in1 or in2
x = float(input())
y = float(input())
if IsPointInArea(x, y):
    print("YES")
else:
    print("NO")
Задача 7. 
Дано действительное положительное число a и целоe число n.

Вычислите an. Решение оформите в виде функции power(a, n).

Стандартной функцией или операцией возведения в степень пользоваться нельзя.
def power(a, n):
    res = 1
    for i in range(abs(n)):
        res *= a
    if n >= 0:
        return res
    else:
        return 1 / res
 
print(power(float(input()), int(input())))
Задача 8. 
Даны два натуральных числа n и m. Сократите дробь nm, то есть выведите два других числа p и q таких, что nm=pq и дробь pq — несократимая.

Решение оформите в виде функции ReduceFraction(n, m), получающая значения n и m и возвращающей кортеж из двух чисел.
a = int(input())
b = int(input())
 
v = a
g = b
while v != 0 and g != 0:
    if v > g:
        v = v % v
    else:
        g = g % v
 
if a == 0:
    c = v
    print(a // c, b // c)
else:
    c = g
    print(a // c, b // c)
Задача 9.
Дано натуральное число n>1. Выведите его наименьший делитель, отличный от 1.

Решение оформите в виде функции MinDivisor(n). Алгоритм должен иметь сложность O(n−−√).

Указание. Если у числа n нет делителя не превосходящего n−−√, то число n — простое и ответом будет само число n
def MinDivisor(n):
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return i
    return n
 
def main():
    n = int(input())
    print(MinDivisor(n))
 
if __name__ == "__main__":
    main()
Задача 10 . 
Дано натуральное число x>1. Проверьте, является ли оно простым. Программа должна вывести слово YES, если число простое и NO, если число составное.

Решение оформите в виде функции IsPrime(x), которая возвращает True для простых чисел и False для составных чисел. Решение должно иметь сложность O(x−−√).
n=int(input('Введите число: '))
def isPrime(n):
    for i in range(2, n):
        if n%i==0:
            resultat='NO'
            break
        else:
            resultat='YES'
    return(resultat)
print(isPrime(n))
Задача 11.
Дано действительное положительное число a и целое неотрицательное число n. Вычислите an не используя циклы и стандартную функцию pow, а используя рекуррентное соотношение an=a⋅an−1.

Решение оформите в виде функции power(a, n).
def power(a, n):
    if n == 0:
        return 1
    else:
        return a * power(a, n - 1)
 
print(power(float(input()), int(input())))
Задача 12.
Напишите рекурсивную функцию sum(a, b), возвращающую сумму двух целых неотрицательных чисел. Из всех арифметических операций допускаются только +1 и -1. Также нельзя использовать циклы.
def summa(a, b):
    a += 1
    b -= 1
    if b > 0:
        return summa(a, b)
    else:
        return a
 
 
print sum(3, 5)
Задача 13.
Напишите функцию phib(n), которая по данному целому неотрицательному n возвращает n-e число Фибоначчи. В этой задаче нельзя использовать циклы - используйте рекурсию.

phib(1) = phib(2) = 1

.phib(n) = phib(n - 1) + phib(n - 2)
def fib(n):
    if n == 1 or n == 2:
        return 1
    else:
        return fib(n - 1) + fib(n - 2)
 
print(fib(int(input())))
Задача 14.
По данным числам n и k (0≤k≤n) вычислите Сkn. Для решения используйте рекуррентное соотношение Ckn=Ck−1n−1+Ckn−1.

Решение оформите в виде функции C(n, k).
def C(n, k):
                if (k == 0 or k == n):
                                return 1
                else:
                                return C(n - 1, k - 1) + C(n - 1, k)
        
        
n, k = map(int, input().split())
print(C(n, k))
Задача 15.
Дана последовательность чисел, завершающаяся числом 0. Найдите сумму всех этих чисел, не используя цикл.
def sum(summary=0):
    num = -1
    try:
        num = int(input())
    except ValueError as err:
        print(err)
        print('Enter the number') 
    else:
        summary += num
    if num != 0:
        return sum(summary)
    return summary
    
print(sum())
Задача 16.
Дана последовательность целых чисел, заканчивающаяся числом 0. Выведите эту последовательность в обратном порядке.

При решении этой задачи нельзя пользоваться массивами и прочими динамическими структурами данных. Рекурсия вам поможет.
def reverse():
    x = int(input())
    if x != 0:
        reverse()
    print(x)
 
reverse()

