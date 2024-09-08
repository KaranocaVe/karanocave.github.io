# cmake大杂烩

## 告诉msvc以指定编码解码

```CMake
if (MSVC)
    target_compile_options(YOURPROJECTNAME PRIVATE /utf-8)
endif ()
```

## 遍历当前目录下的 .cpp 文档并分别生成可执行文档

```CMake
file(GLOB_RECURSE CPP_FILES "${CMAKE_SOURCE_DIR}/*.cpp")

foreach(CPP_FILE ${CPP_FILES})
    get_filename_component(FILE_NAME ${CPP_FILE} NAME_WE)
    add_executable(${FILE_NAME} ${CPP_FILE})
endforeach()
```