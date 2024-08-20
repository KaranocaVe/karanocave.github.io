# cmake大杂烩

## 告诉msvc以指定编码解码

```CMake
if (MSVC)
    # 设置 MSVC 使用 UTF-8 编码
    target_compile_options(untitled PRIVATE /utf-8)
endif ()
```