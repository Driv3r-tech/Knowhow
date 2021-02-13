
# Ключевые слова
>Важное примечание: вывод ошибок сделан для того, чтобы понятней была работа кода.

## inline
Позволяет компилятору ***не выделять память*** и просто скопировать встроенный код функции в вызывающем месте.

```kotlin
inline fun example( str : String, mycall :(String)-> Unit) {

    mycall(str)

}

fun main() {

    print("My name is ")
    example("James",::print)

} 
```
**Вывод**
```
My name is James
```

##
##

## ~static~ / companion object
Позволяет переменной ***задействовать память только один раз***. Если какой-либо объект изменяет значение статической переменной, последняя сохраняет свое значение.

**main.kt**
```kotlin
package com.main

import com.classes.Person

fun main(){

    println("Age "+ Person.age)
    println("ID: "+ Person.id) // error

    val bob: Person = Person()
    println("Bob ID: "+ bob.id)
    
}
```
**person.kt**
```kotlin
package com.classes

class Person {
    companion object {
        var age : Int = 7
    }
    var id : Int = 9
}
```
**Вывод**
```
Age: 7
Unresolved reference: id
Bob ID: 9
```


##
##

