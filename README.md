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
