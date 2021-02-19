
# Ключевые слова
## Содержание

0. [inline](#inline)
1. [static / companion object](#static-or-companion-object)
2. [infix](#infix)
3. [reified](#reified)

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
[Содержание](#Содержание)
##
##

## static or companion object
Позволяет переменной ***задействовать память только один раз***. Если какой-либо объект изменяет значение статической переменной, последняя сохраняет свое значение. Доступ к переменной ***глобальный*** (отсылка к _порождающему паттерну проектирования **singleton**_).

**main.kt**
```kotlin
package com.main

import com.classes.Person

fun main(){

    println("Age: "+ Person.age)
    // println("ID: "+ Person.id) // error - Unresolved reference: id

    val bob: Person = Person()
    // println("Bob age: "+ bob.age) // error - Unresolved reference: age
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
Bob ID: 9
```
[Содержание](#Содержание)
##
##

## infix
Позволяет сделать код на вид таким, как выглядит **естественный язык**.

```kotlin
val ice = "ice"
val juice = "juice"
val coffee = "coffee"

infix fun String.mix(str: String): String {
    
    when (setOf(this,str)){
    
        setOf(juice, coffee) -> return "Boyfriend"
        setOf(ice, coffee) -> return "Iced coffee"
        setOf(ice, juice) -> return ice+juice
        setOf(coffee, ice+juice) -> return "Tiger"
        else -> return "-"
        
    }
    
}

fun main() {
    
    val coctail = ice mix juice mix coffee 
    println("My coctail: $coctail")
    
}
```
**Вывод**
```
My coctail: Tiger
```
[Содержание](#Содержание)
##
##

## reified
Использоуется только в```inline```функциях. ***Сохраняет в памяти доступ к объявленному типу***.

```kotlin
var _map = arrayOf("Paris", 2_000, 'v')

inline fun <reified T> getItemFromMap(key: Int): T? {
    
    val item = _map.get(key)
    println(item)
    
    if(T::class == item::class) {
        return item as T
    }
    else { 
        return null
    }
    
}

fun main() {
    
    val list: String = getItemFromMap(1)?: "<Undefined>"
    println(list)
 
}
```
**Вывод**
```
2000
<Undefined>
```
[Содержание](#Содержание)
##
##

## 


