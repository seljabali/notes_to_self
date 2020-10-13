# Table of Contents  
- [1. Constructors](#1-constructors)
- [2. Getters & Setters](#2-getters-&-setters)
- [3. Generics](#3-generics)
- [4. Scopes](#4-scopes)
- [5. This](#5-this)
- [6. Elvis Operator](#6-elvis-operator)

# 1. Constructors
```kotlin
class Foo(val bar: String) {
  val fooBar = "foo $bar"
  val nom: String

  init {
    nom = "nom $bar"
    nom.capitalize()
  }

  constructor(lol: String, count: Int) : this(lol)  {      
  }
}
```

# 2. Getters & Setters
```kotlin
val cookieCount: String get() {
    if (jar.isEmpty()) {
        return "Grab some cookies"
    }
    return "No cookies for you"
}

val cookie: String get() = "Cookie time"

var cookie: String = ""
    get() = field
    set(value) {
        field = value
        buildApi()
        }
```

# 3. Generics
Invariant:
Generic types in Java are invariant, meaning that List<String> is not a subtype of List<Object>.
```java
List<String> strs = new ArrayList<String>();
List<Object> objs = strs; // !!! The cause of the upcoming problem sits here. Java prohibits this!
objs.add(1); // Here we put an Integer into a list of Strings
String s = strs.get(0); // !!! ClassCastException: Cannot cast Integer to String
```
Covariant:

# 4. Loops
```kotlin
for (index in 0 until stockPrices.size) {
}

for (index in stockPrices.indices) {
}

for ((index, element) in stockPrices.iterator().withIndex()) {
}

for stockPrices.forEachIndexed { index, element ->
}
```

# 5. This
```kotlin
foo.apply {
  this.bar = this@OuterClass.bar
}
```

# 6. Elvis Operator
```kotlin
val foo = bar ?: run {
  ...
}
```
