# Inside Jetpack Compose diagram

If you find any problems, please create an issue.

This diagram illustrates how Jetpack Compose handles changing the state of the following code.

The entire code is [here](https://github.com/takahirom/simple-compose-for-learning-inside-compose/blob/873568ae64965d50cd68abe238e1c5dcb6b30fcc/src/main/kotlin/com/github/takahirom/compose/Main.kt#L82-L92).


```kotlin
@Composable
fun Content() {
    var state by remember { mutableStateOf(true) }
    LaunchedEffect(Unit) {
        delay(3000)
        state = false
    }
    if (state) {
        Node1()
    }
    Node2()
}
```

```
RootNode
├── Node1(value=node1)
└── Node2(value=node2)
```

↓

```
RootNode
└── Node2(value=node2)
```


![diagram](./diagram.png)
