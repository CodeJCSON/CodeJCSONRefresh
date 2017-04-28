# CodeJCSONRefresh

[开发者](#nihao)








##世界和平


}
```

一个`do`语句创建了一个新的包含作用域,使得错误能被传播到一个或多个`catch`从句。

这里有一个错误处理如何用来应对不同错误条件的例子。

```swift
func makeASandwich() throws {
    // ...
}
 
do {
    try makeASandwich()
    eatASandwich()
} catch SandwichError.outOfCleanDishes {
    washDishes()
} catch SandwichError.missingIngredients(let ingredients) {
    buyGroceries(ingredients)
}
```

在此例中，`makeASandwich()`（做一个三明治）函数会抛出一个错误消息如果没有干净的盘子或者某个原料缺失。因为 `makeASandwich()` 抛出错误，函数调用被包裹在 `try` 表达式中。将函数包裹在一个 `do` 语句中，任何被抛出的错误会被传播到提供的 `catch` 从句中。

如果没有错误被抛出，`eatASandwich()` 函数会被调用。如果一个匹配 `SandwichError.outOfCleanDishes` 的错误被抛出，`washDishes()` 函数会被调用。如果一个匹配 `SandwichError.missingIngredients` 的错误被抛出，`buyGroceries(_:)` 函数会被调用，并且使用 `catch` 所捕捉到的关联值 `[String]` 作为参数。

抛出，捕捉，以及传播错误会在[错误处理](./18_Error_Handling.html)章节详细说明。

<a name="assertions"></a>
## 断言

可选类型可以让你判断值是否存在，你可以在代码中优雅地处理值缺失的情况。然而，在某些情况下，如果值缺失或者值并不满足特定的条件，你的代码可能没办法继续执行。这时，你可以在你的代码中触发一个 *断言（assertion）* 来结束代码运行并通过调试来找到值缺失的原因。







<a name="nihao"></a>
#开发者
