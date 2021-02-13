
# Ключевые слова

## inline
Позволяет компилятору не выделять память и просто скопировать встроенный код функции (<b class="keyword">example</b>) в вызывающем месте (<b class="keyword"></b>).

```kotlin
inline fun example( str : String, mycall :(String)-> Unit) {

    mycall(str)

}

fun main() {

    print("My name is ")

    example("James",::print)

} 
```

>My name is James


