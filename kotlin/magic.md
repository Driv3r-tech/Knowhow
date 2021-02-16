# Особенности языка

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

##
##

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

##
##

## Сложные лямбды
Функция без имени, могут быть использованы как аргументы.

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

##
##

## Скоро обновление
