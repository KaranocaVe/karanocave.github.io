# 速查表

## 基本类型
Microsoft C++ 32 位和 64 位编译器可识别本文后面的表中的类型。

- **`int`** (**`unsigned int`**)
- **`__int8`** (**`unsigned __int8`**)
- **`__int16`** (**`unsigned __int16`**)
- **`__int32`** (**`unsigned __int32`**)
- **`__int64`** (**`unsigned __int64`**)
- **`short`** (**`unsigned short`**)
- **`long`** (**`unsigned long`**)
- **`long long`** (**`unsigned long long`**)

如果其名称以两个下划线 (`__`) 开始，则数据类型是非标准的。

下表中指定的范围均包含起始值和结束值。

| 类型名称                     | 字节                | 其他名称                                                 | 值的范围                                                                                                                                             |
|:-------------------------|:------------------|:-----------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| **`int`**                | 4                 | **`signed`**                                         | -2,147,483,648 到 2,147,483,647                                                                                                                   |
| **`unsigned int`**       | 4                 | **`unsigned`**                                       | 0 到 4,294,967,295                                                                                                                                |
| **`__int8`**             | 1                 | **`char`**                                           | -128 到 127                                                                                                                                       |
| **`unsigned __int8`**    | 1                 | **`unsigned char`**                                  | 0 到 255                                                                                                                                          |
| **`__int16`**            | 2                 | **`short`**, **`short int`**, **`signed short int`** | -32,768 到 32,767                                                                                                                                 |
| **`unsigned __int16`**   | 2                 | **`unsigned short`**，**`unsigned short int`**        | 0 到 65,535                                                                                                                                       |
| **`__int32`**            | 4                 | **`signed`**, **`signed int`**, **`int`**            | -2,147,483,648 到 2,147,483,647                                                                                                                   |
| **`unsigned __int32`**   | 4                 | **`unsigned`**，**`unsigned int`**                    | 0 到 4,294,967,295                                                                                                                                |
| **`__int64`**            | 8                 | **`long long`**，**`signed long long`**               | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807                                                                                           |
| **`unsigned __int64`**   | 8                 | **`unsigned long long`**                             | 0 到 18,446,744,073,709,551,615                                                                                                                   |
| **`bool`**               | 1                 | 无                                                    | **`false`** 或 **`true`**                                                                                                                         |
| **`char`**               | 1                 | 无                                                    | -128 到 127（默认）  0 到 255（在通过使用 [`/J`](https://learn.microsoft.com/zh-cn/cpp/build/reference/j-default-char-type-is-unsigned?view=msvc-170) 进行编译时） |
| **`signed char`**        | 1                 | 无                                                    | -128 到 127                                                                                                                                       |
| **`unsigned char`**      | 1                 | 无                                                    | 0 到 255                                                                                                                                          |
| **`short`**              | 2                 | **`short int`**，**`signed short int`**               | -32,768 到 32,767                                                                                                                                 |
| **`unsigned short`**     | 2                 | **`unsigned short int`**                             | 0 到 65,535                                                                                                                                       |
| **`long`**               | 4                 | **`long int`**，**`signed long int`**                 | -2,147,483,648 到 2,147,483,647                                                                                                                   |
| **`unsigned long`**      | 4                 | **`unsigned long int`**                              | 0 到 4,294,967,295                                                                                                                                |
| **`long long`**          | 8                 | 无（但与 **`__int64`** 等效）                               | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807                                                                                           |
| **`unsigned long long`** | 8                 | 无（但与 **`unsigned __int64`** 等效）                      | 0 到 18,446,744,073,709,551,615                                                                                                                   |
| **`enum`**               | 多种多样              | 无                                                    |                                                                                                                                                  |
| **`float`**              | 4                 | 无                                                    | 3.4E +/- 38（7 位数）                                                                                                                                |
| **`double`**             | 8                 | 无                                                    | 1.7E +/- 308（15 位数）                                                                                                                              |
| **`long double`**        | 与 **`double`** 相同 | 无                                                    | 与 **`double`** 相同                                                                                                                                |
| **`wchar_t`**            | 2                 | **`__wchar_t`**                                      | 0 到 65,535                                                                                                                                       |

根据使用方式， **`__wchar_t`** 的变量指定宽字符类型或多字节字符类型。 在字符或字符串常量前使用 `L` 前缀以指定宽字符类型常量。

**`signed`** 和 **`unsigned`** 是可用于任何整型（ **`bool`**除外）的修饰符。 请注意，对于重载和模板等机制而言，**`char`**、**`signed char`** 和 **`unsigned char`** 是三种不同的类型。

**`int`** 和 **`unsigned int`** 类型具有四个字节的大小。 但是，由于语言标准允许可移植代码特定于实现，因此该代码不应依赖于 **`int`** 的大小。

## 运算符优先级

| 操作符类型 | 操作符                             | 关联规则 |
|-------|---------------------------------|------|
| 关联操作符 | () [] -> .                      | 从左到右 |
| 一元操作符 | ！ - ++ -- + - (type) * & sizeof | 从右到左 |
| 乘法和除法 | * / %                           | 从左到右 |
| 加法和减法 | + -                             | 从左到右 |
| 位移操作符 | >> <<                           | 从左到右 |
| 关系操作符 | < <= > >=                       | 从左到右 |
| 相等比较符 | == !=                           | 从左到右 |
| 位操作符  | &                               | 从左到右 |
| 位操作符  | ^                               | 从左到右 |
| 位操作符  | \|                              | 从左到右 |
| 逻辑运算符 | &&                              | 从左到右 |
| 逻辑运算符 | \|\|                            | 从左到右 |
| 条件运算符 | ?:                              | 从右到左 |
| 赋值运算符 | = 及其派生                          | 从右到左 |
| 序列点   | ,                               | 从左到右 |

## 函数

## scanf
> **长度修饰符**
>
> | 长度修饰符        | 适用的转换说明符               | 含义                              |
> |--------------|------------------------|---------------------------------|
> | hh           | d、i、o、u、x、X、n          | signed char or unsigned char    |
> | h            | d、i、o、u、x、X、n          | short or unsigned short         |
> | l（ell）       | d、i、o、u、x、X、n          | long or unsigned long           |
> | l（ell）       | a, A, e, E, f, F, g, G | double                          |
> | l（ell）       | c、s、[                  | wchar_t                         |
> | ll (ell-ell) | d、i、o、u、x、X、n          | long long or unsigned long long |
> | L            | a, A, e, E, f, F, g, G | long double                     |
> | j            | d、i、o、u、x、X、n          | intmax_t or uintmax_t           |
> | z            | d、i、o、u、x、X、n          | size_t                          |
> | t            | d、i、o、u、x、X、n          | ptrdiff_t                       |
>

> **转换说明**
>
> | 转换说明符      | 含义                 |
> |------------|--------------------|
> | d          | 可选符号十进制整数          |
> | i          | 可选符号整数             |
> | o          | 可选符号八进制整数          |
> | u          | 无符号十进制整数           |
> | x          | 可选符号十六进制整数         |
> | a, e, f, g | 可选带符号的浮点数、无穷大或 NaN |
> | s          | 字符串                |
> | c          | 由字段宽度指定的数字的字节序列    |
> | p          | 匹配实现定义的序列集         |
> | n          | 不消耗任何输入            |
> | C          | lc                 |
> | S          | ls                 |
> | %          | 解决%字符的匹配问题         |
>

