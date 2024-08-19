# 无法找到标识符scanf

环境VisualStudio 2022

提示无法找到标识符scanf，但是可以找到printf，推测stdio.h文件损坏

解决方案是彻底重装MSVC或者从别处找找来MSVC的stdio.h文件（必须是MSVC的，不能是Mingw的）

一些见解：

VS没有保护标准库的机制，而Clion默认标准库是只可读的