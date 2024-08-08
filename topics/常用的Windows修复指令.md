# 常用的Windows维护指令

## 修复系统
```Shell
DISM.exe /Online /Cleanup-image /Scanhealth
DISM.exe /Online /Cleanup-image /Checkhealth
DISM.exe /Online /Cleanup-image /Restorehealth
sfc /scannow
```

## 修复应用
```Shell
Set-ExecutionPolicy Unrestricted
Get-AppXPackage -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}
```

## 安装所有MSVC运行时库

```Shell
winget install --id Microsoft.VCRedist.2005.x64 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2005.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2008.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2008.x64 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2010.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2010.x64 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2012.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2012.x64 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2013.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2013.x64 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCLibs.Desktop.14 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2015+.x86 --silent --accept-package-agreements --accept-source-agreements; winget install --id Microsoft.VCRedist.2015+.x64 --silent --accept-package-agreements --accept-source-agreements
```

## 补全DirectX

```Shell
winget.exe install --id Microsoft.DirectX --exact --accept-source-agreements --silent --disable-interactivity --accept-package-agreements```