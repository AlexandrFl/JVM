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

![avatar](https://sun9-79.userapi.com/impg/VX_iEFHwqMNTmVv_w7gKPNOLEQnTHGLA_AeJwA/my4jJt65BdU.jpg?size=334x334&quality=95&sign=77be0b58d150aea65f848b85cd636486&type=album) 

В момент вызова метода main() создается фрейм в стеке
1. В фрейме main() выделяется область памяти для хранения примитивного значения i типа int.
2. В heap создается объект класса Object, а в фрейме main() создается ссылочная переменная o.
3. В heap создается объект класса-обертки Integer, а в фрейме main() создается ссылочная переменная ii.
4. В стеке выделяется область памяти для метода printAll(). В нем также создаются примитивное значение i типа int и ссылочные переменные o и ii.
5. В heap создается объект класса-обертки Integer, а в printAll() ссылочная переменная uselessVar.
6. 1) В стеке выделяется область памяти для метода toString() и в флейме создается ссылочная переменная o и ссылочная переменная x. В heap создается объект класса String. Этот объект связан с объектом Object и с переменной х
   2) В стеке выделяется область памяти для метода println() и в флейме создается ссылочная переменная ii, x, xx и примитивная переменная i типа int. В heap создается объект класса String1. Этот объект связан с объектом String и Integer и переменной хх
7. В heap создается объект класса String2 (finished). В стеке выделяется область памяти для метода println() и в фрейме создается ссылочная переменная x которая ссылается на String 2.

![avatar](https://sun9-22.userapi.com/impg/iNTTw8t42qD61gT-SgHgBdgyRFOw7BpNBm-WpA/5Nu4JTq7l8Q.jpg?size=1027x819&quality=95&sign=c7118dd62c721c446433b412644faf99&type=album)

# Задание 2

![avatar](https://sun9-42.userapi.com/impg/DwxO20d5kzW-LXJEz2iq_E0DHnVYzeCKxfZMHg/udYdm281Vwg.jpg?size=1721x685&quality=95&sign=b261fdea51265ba9669ed522860ccdbb&type=album)

![avatar](https://sun9-78.userapi.com/impg/5-ahbeWvkFJFUPSuHyyHvXNuFbYtNotvl_nL3w/2phXo8knqtE.jpg?size=1304x690&quality=95&sign=f04a347b434c95375e105cc13a93a27c&type=album)

![avatar](https://sun9-88.userapi.com/impg/GnBIcpBxIT_rqGtv6Ow1dbaH452DSZhbtaL9YA/DruHytHrAVU.jpg?size=1852x694&quality=95&sign=7904a0cdbada4ca0b3f33098c2650a46&type=album)