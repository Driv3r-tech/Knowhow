# Особенности языка

## Extension Functions 
Мы можем расширить класс, ***не изменяя его***, и добавить новый метод.

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
Мы можем расширить класс, ***не изменяя его***, и добавить новое свойство.

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
