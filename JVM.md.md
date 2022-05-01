Вначале JVM с помощью ClassLoader загрузит классы. 
Application ClassLoader загрузит класс JvmComprehension. 
Bootstrap ClassLoader загрузит классы System, Object и другие системные. 
Создаётся стековая память(Stack Memory).

public class JvmComprehension {

public static void main(String[] args) { // создает фрейм main в Stack Memory
    int i = 1;                      // 1 создает переменую в Stack Memory
    Object o = new Object();        // 2 создает в heap объект "o"
    Integer ii = 2;                 // 3 создает в heap объект "ii"
    printAll(o, i, ii);             // 4 создает фрейм  printAll в Stack Memory
    System.out.println("finished"); // 7 создает фрейм  toString в Stack Memory
}
Сборщик мусора очистит объекты которые становятся недоступными при дальнейшем исполнении программы.

private static void printAll(Object o, int i, Integer ii) {
    Integer uselessVar = 700;                   // 5 создает в heap объект "uselessVar"
    System.out.println(o.toString() + i + ii);  // 6 создает фрейм toString в Stack Memory
}
}