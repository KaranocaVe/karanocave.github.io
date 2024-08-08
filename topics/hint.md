# hint

- 词法闭包
- 匿名函数
- 
-  `~/` Divide, returning an integer result

- | Operator | Meaning                                    |
  | :------- | :----------------------------------------- |
  | `as`     | Typecast (也被用于指定库前缀)              |
  | `is`     | True if the object has the specified type  |
  | `is!`    | False if the object has the specified type |

- 
```Javascript
// 如果b为空时，将变量赋值给b，否则，b的值保持不变。
b ??= value;
```
-
```Javascript
condition ? expr1 : expr2
//如果条件为 true, 执行 expr1 (并返回它的值)： 否则, 执行并返回 expr2 的值。
expr1 ?? expr2
//如果 expr1 是 non-null， 返回 expr1 的值； 否则, 执行并返回 expr2 的值。
```
- 级联运算符 (..),级联操作符只能在方法返回调用对象本身时使用

>**提示**
> 严格的来讲， “两个点” 的级联语法不是一个运算符。 它只是一个 Dart 的特殊语法。
>  {style="note"}

- 不管是否抛出异常， finally 中的代码都会被执行。 如果 catch 没有匹配到异常， 异常会在 finally 执行完成后，再次被抛出。
- 一个常量上下文中的 const 关键字可以被省略。
- Deferred loading (也称之为 lazy loading) 可以让应用在需要的时候再加载库。