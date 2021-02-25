# Hot :fire: and desired Kotlin issues


## Public-private field

[KT-14663](https://youtrack.jetbrains.com/issue/KT-14663)

Allowing to expose field as immutable and keep it accessible as a mutable inside the class.

**Now:**
```kotlin
class ViewModel {

  private var _data: MutableList<String> = // ...
  val data: List<String> = _data

  fun insertToData(item: String) {
    _data += item
  }

}
```

**Will be:**
```kotlin
class ViewModel {

  private val data: MutableList<String> = // ...
    public get(): List<String>

  fun insertToData(item: String) {
    data += item
  }

}
```

