# Задание 1

```java
public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1
        Object o = new Object();        // 2
        Integer ii = 2;                 // 3
        printAll(o, i, ii);             // 4
        System.out.println("finished"); // 7
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5
        System.out.println(o.toString() + i + ii);  // 6
    }
}

```
Подсистема загрузчиков классов подгружает класс JvmComprehension и системные классы. Далее происходит проверка валидности кода, подготовка примитивов в статических полях и связывание ссылок на другие классы. Затем происходит инициализация статических полей. Затем данные о классе и константы переносятся в Metaspace.

![avatar](D:\Java Project\JVM\Схемы\m.png) 

В момент вызова метода main() создается фрейм в стеке
1. В фрейме main() выделяется область памяти для хранения примитивного значения i типа int.
2. В heap создается объект класса Object, а в фрейме main() создается ссылочная переменная o.
3. В heap создается объект класса-обертки Integer, а в фрейме main() создается ссылочная переменная ii.
4. В стеке выделяется область памяти для метода printAll(). В нем также создаются примитивное значение i типа int и ссылочные переменные o и ii.
5. В heap создается объект класса-обертки Integer, а в printAll() ссылочная переменная uselessVar.
6. 1) В стеке выделяется область памяти для метода toString() и в флейме создается ссылочная переменная o и ссылочная переменная x. В heap создается объект класса String. Этот объект связан с объектом Object и с переменной х
   2) В стеке выделяется область памяти для метода println() и в флейме создается ссылочная переменная ii, x, xx и примитивная переменная i типа int. В heap создается объект класса String1. Этот объект связан с объектом String и Integer и переменной хх
7. В heap создается объект класса String2 (finished). В стеке выделяется область памяти для метода println() и в фрейме создается ссылочная переменная x которая ссылается на String 2.

![avatar](D:\Java Project\JVM\Схемы\4.png)

# Задание 2

![avatar](D:\Java Project\JVM\Схемы\Classes.png)

![avatar](D:\Java Project\JVM\Схемы\Metaspace.png)

![avatar](D:\Java Project\JVM\Схемы\heap.png)