# :fire: Hot, desired and long-awaited Kotlin-related issues that need your vote!

:warning: _This list is community-driven and not affiliated with JetBrains._ :warning:

_Do we miss something? Let us [know](https://github.com/dector/kotlin-issues-to-like/issues)._

---

## :eyes: [Readability]

### Public-private field

**Issue**: [KT-14663](https://youtrack.jetbrains.com/issue/KT-14663)

**Status**: N/A.

**What?**: Allowing to expose field as immutable and keep it accessible as a mutable inside the class.

**How are we doing this now?**

```kotlin
class ViewModel {

  private var _data: MutableList<String> = // ...
  val data: List<String> = _data

  fun insertToData(item: String) {
    _data += item
  }

}
```

**What do we want?**

```kotlin
class ViewModel {

  private val data: MutableList<String> = // ...
    public get(): List<String>

  fun insertToData(item: String) {
    data += item
  }

}
```



## :package: [Stdlib]



### `toString()` with precision for numbers

**Issue**: [KT-9374](https://youtrack.jetbrains.com/issue/KT-9374)

**Status**: N/A.

**What?**: Converting `Double`/`Float` to String with certain precision.

**How are we doing this now?**

```kotlin
java.lang.String.format("%.2f", 3.141592)
```

**What do we want?**

```kotlin
3.141592.toString(precision = 2)
```



## :steam_locomotive: [Performance]

### `isSubtypeOf`/`isSupertypeOf` without reflection

**Issue**: [KT-32956](https://youtrack.jetbrains.com/issue/KT-32956)

**Status**: N/A.

Also this will work on non-JVM targets.

