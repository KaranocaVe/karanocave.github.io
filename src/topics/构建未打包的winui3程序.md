# 构建未打包的WinUI3程序

简单来说就是no more MSIX，我要双击exe直接运行！

[SRC](https://learn.microsoft.com/zh-cn/windows/apps/winui/winui3/create-your-first-winui3-app)

## 具体操作步骤

### 编辑项目的vcxproj文件

找到`<PropertyGroup>`标签。

1. 首先关闭Appx打包，这个是必须的
```xml
    <AppxPackage>false</AppxPackage>
```

2. 设置不打包
```xml
		<WindowsPackageType>None</WindowsPackageType>
```

3. 如果你希望Client不安装WindowsAppSDK也能直接运行，请开启自包含
```xml
		<WindowsAppSDKSelfContained>true</WindowsAppSDKSelfContained>
```

### 构建

直接使用生成解决方案即可，结果会出现在与你的sln文件同级的{架构}文件夹中。