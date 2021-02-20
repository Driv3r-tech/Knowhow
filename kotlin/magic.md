# Особенности языка
## Содержание

1. [Extension Functions](#extension-functions)
2. [Extension Properties](#extension-properties)
3. [Сложные лямбды](#Сложные-лямбды)
4. [trailing lambda](#trailing-lambda)

## Extension Functions
Мы можем расширить класс, ***не изменяя его***, и добавить _новый метод_.

```kotlin
private fun String.exampleDeleteSpaces(): String {

    return this.replace(" ", "")
    
}

fun main() {

    println("H el lo   , W or ld".exampleDeleteSpaces()) 

} 
```
**Вывод**
```
Hello,World
```
[Содержание](#содержание)

____

## Extension Properties
Мы можем расширить класс, ***не изменяя его***, и добавить _новое свойство_.

```kotlin
private val String.first: Char
    get() {
        
        return this[2]
        
    }
        
fun main() {
        
    print("Kotlin".first)

} 
```
**Вывод**
```
t
```
[Содержание](#содержание)

____

## Сложные лямбды
Краткость - сестра таланта.

**До**
 ```kotlin
fun main() {

    val builder = StringBuilder()
    builder.append("Hello ")
    builder.append("World ")
    builder.append("Kotlin ")
    builder.append("The Best ")
    print(builder.toString())
    
}
 ```
 
**После**
```kotlin
fun main() {

    StringBuilder().apply {

    append("Hello ")
    append("World ")
    append("Kotlin ")
    append("The Best")
    
    }.let {
        print(it.toString())
    }
    
}
```
**Прототип**
```kotlin

public inline fun <T> T.apply(block: T.() -> Unit): T{

    block()
    
    return this
}

public inline fun <T, R> T.let(block: (T) -> R): R = block(this)

```
**Вывод**
```
Hello World Kotlin The Best
```
[Содержание](#содержание)

____

## trailing lambda
Если последний параметр является функцией, то лямбда-выражение может быть заключена в **фигурные скобки**.

```kotlin
inline fun <R> R.example(
    initial: R,
    operation: (acc: R, e: R) -> R
): R = operation (initial, this)

fun main() {

    val test = 5
    val result = test.example(3) { acc, e -> acc + e }
    println("Result: $result")
    
}
```
**Вывод**
```
Result: 8
```
[Содержание](#содержание)

____

## 
