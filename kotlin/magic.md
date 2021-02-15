# Магические функции

## Extension Functions 
Мы можем расширить класс, ***не изменяя его***, и добавить новый метод или свойство.

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
