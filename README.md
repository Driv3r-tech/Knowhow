# Knowhow
 Like wiki, but hotter

## Knowhow

### Конструкторы

```kotlin
class Empty
```

Класс в <b>Kotlin</b> может иметь основной конструктор (**primary constructor**)

<b class="keyword">init</b>.


Для более подробной информации по данному вопросу см. "[Модификаторы доступа](visibility-modifiers.html#constructors)".

>**Примечание**: В виртуальной машине JVM компилятор генерирует дополнительный конструктор без параметров в случае, если все параметры основного конструктора имеют значения по умолчанию. Это делает использование таких библиотек, как <b>Jackson</b> и <b>JPA</b>, более простым в языке <b>Kotlin</b>, так как они используют пустые конструкторы при создании экземпляров классов.
>
>```kotlin
>class Customer(val customerName: String = "")
>```


У `Any` есть три метода: `equals()`, `hashCode()` и `toString()`. 

