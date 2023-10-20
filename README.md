Проект "Decimal"
Описание проекта
Проект "Decimal Calculator" представляет собой реализацию арифметических операций и преобразований с десятичными числами в формате Decimal. Decimal представляет собой число, состоящее из 96-разрядного целого числа и коэффициента масштабирования. Проект также включает в себя операции сравнения, округления и преобразования между Decimal и другими числовыми типами.

Техническое задание
Двоичное представление Decimal состоит из 1-разрядного знака, 96-разрядного целого числа и коэффициента масштабирования.
Коэффициент масштабирования неявно равен числу 10 в степени от 0 до 28.
Decimal представляется как четырехэлементный массив 32-разрядных целых чисел.
Арифметические операторы
Сложение: int s21_add(s21_decimal value_1, s21_decimal value_2, s21_decimal *result)
Вычитание: int s21_sub(s21_decimal value_1, s21_decimal value_2, s21_decimal *result)
Умножение: int s21_mul(s21_decimal value_1, s21_decimal value_2, s21_decimal *result)
Деление: int s21_div(s21_decimal value_1, s21_decimal value_2, s21_decimal *result)
Операторы сравнения
Меньше: int s21_is_less(s21_decimal, s21_decimal)
Меньше или равно: int s21_is_less_or_equal(s21_decimal, s21_decimal)
Больше: int s21_is_greater(s21_decimal, s21_decimal)
Больше или равно: int s21_is_greater_or_equal(s21_decimal, s21_decimal)
Равно: int s21_is_equal(s21_decimal, s21_decimal)
Не равно: int s21_is_not_equal(s21_decimal, s21_decimal)
Преобразователи
Из int: int s21_from_int_to_decimal(int src, s21_decimal *dst)
Из float: int s21_from_float_to_decimal(float src, s21_decimal *dst)
В int: int s21_from_decimal_to_int(s21_decimal src, int *dst)
В float: int s21_from_decimal_to_float(s21_decimal src, float *dst)
Другие функции
Округление вниз: int s21_floor(s21_decimal value, s21_decimal *result)
Округление: int s21_round(s21_decimal value, s21_decimal *result)
Отбрасывание дробной части: int s21_truncate(s21_decimal value, s21_decimal *result)
Изменение знака на противоположный: int s21_negate(s21_decimal value, s21_decimal *result)
Код ошибок
Функции возвращают следующие коды ошибок:

0: Операция выполнена успешно.
1: Число слишком велико или равно бесконечности.
2: Число слишком мало или равно отрицательной бесконечности.
3: Деление на 0.
4: Ошибка конвертации.
Примечания:

При операциях с числами, не вмещающимися в мантиссу, используется банковское округление.
При преобразовании чисел типа float меньше 1e-28 возвращается ошибка.
При преобразовании чисел типа float больше 79,228,162,514,264,337,593,543,950,335 возвращается ошибка.
При преобразовании числа типа float, округление происходит до ближайшего значения с не более чем 7 значимыми цифрами.
При преобразовании из числа типа decimal в тип int, дробная часть отбрасывается.
Пример структуры Decimal
c
Copy code
typedef struct 
{
    int bits[4];
} s21_decimal;
Проект "Decimal Calculator" предоставляет возможность работы с десятичными числами, проведения арифметических операций и преобразований, а также обработки ошибок.




