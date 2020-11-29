[Documentation](https://doc.insert-koin.io/#/)

### Defining Modules with similar return type
Definition:
```kotlin
single<Box<Foo>>(named("foo")) {
    ObjectBox.get().boxFor(Foo::class.java)
}

single<Box<Bar>>(named("bar")) {
    ObjectBox.get().boxFor(Bar::class.java)
}

single<BoxStore> {
    MyObjectBox.builder().androidContext(androidContext().applicationContext).build()
}
```
Usage:
```kotlin
val fooBox: Box<Foo> by inject(named("foo"))
val boxStore by inject<BoxStore>()
```

### Lazy vs Computed loading
lazy: loaded once on instance creation
```kotlin
val api: ApiService by inject(named("api"))
```
computed: always fetches instance on each call
```kotlin
val api: ApiService get() = get(named("api"))
```

### Injecting on non-fragments & activities
```kotlin
import org.koin.core.KoinComponent

object Bar : KoinComponent {
  val fooBox: Box<Foo> by inject(named("foo"))
}
```
or
```kotlin
inline fun <reified T: Any> getKoinInstance(): T {
    return object : KoinComponent {
        val value: T by inject()
    }.value
}

val fooBox: Box<Foo> = getKoinInstance<Box<Foo>>()
```
