# 在Windows上快速部署一个OpenGL开发环境

## 材料准备
- 安装[Windows SDK](https://developer.microsoft.com/zh-cn/windows/downloads/windows-sdk/)，它包含了OpenGL本体
- 下载编译好的或者自己编译[GLFW](https://www.glfw.org/download.html)
- 下载[Glad](https://glad.dav1d.de/#language=c-debug&specification=gl&api=gl%3D4.6&api=gles1%3Dnone&api=gles2%3Dnone&api=glsc2%3Dnone&profile=core&loader=on)

## 配置项目
把上面的include和lib放到恰当的文件夹，然后配置cmakelists.txt，模板如下：

```CMake
cmake_minimum_required(VERSION 3.28)
project(testfield)

set(CMAKE_CXX_STANDARD 17)

include_directories(${PROJECT_SOURCE_DIR}/glfw/include)
link_directories(${PROJECT_SOURCE_DIR}/glfw/lib)

include_directories(${PROJECT_SOURCE_DIR}/glad/include)

add_executable(MainWindow main.cpp
        glad/src/glad.c)

find_package(OpenGL REQUIRED)

include_directories(${OPENGL_INCLUDE_DIR})

target_link_libraries(MainWindow glfw3 ${OPENGL_gl_LIBRARY} gdi32 user32 shell32)
```

请确保将main.cpp换成你源码的文件名。