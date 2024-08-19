# 迂回修改const时遇到的一个问题

## 问题的起因

请看这两段代码
```C
int main() {
    int a = 1;
    const int b = 2;
    //&b;
    int *p = &a;
    p--;
    *p = 3;
}
```
上面这段代码在几乎所有的编译器中，结果都是b值没有改变。

而下面这段代码，则依据环境的不同有不同的结果，b可能不变，也有可能变成3。
```C
int main() {
    int a = 1;
    const int b = 2;
    &b;
    int *p = &a;
    p--;
    *p = 3;
}
```

## 解答
问题的原因可以先参考这两篇文章

[【C++ 关键字 类型限定符 】揭秘C++编程中的神秘元素：深入了解volatile关键字的强大作用](http://t.csdnimg.cn/svCJi)

[C++ 防止编译器优化const和constexpr的学习](http://t.csdnimg.cn/eATu0)