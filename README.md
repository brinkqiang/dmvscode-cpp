# dmvscode-cpp

# vscode cpp msvc 单文件调试 环境设置手册

# 安装插件

![Mobile Preview](/images/codelldb.png)
![Mobile Preview](/images/cpp-runner.png)

# 设置参数

## vscode -> 文件 -> 首选项 -> 设置 -> 搜索 

![Mobile Preview](/images/useMsvc.png)
![Mobile Preview](/images/msvcBatchPath.png)

# 测试

## 打开测试工程

目录
./test/
  - main.cpp
```
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}

```

## 点击编译
![Mobile Preview](/images/build.png)

## 断点 调试(F5)

![Mobile Preview](/images/debug.png)

# cline 设置

## 安装 PowerShell7
```
winget install --id Microsoft.PowerShell
```

管理员权限 运行powershell 
Get-ExecutionPolicy
如果输出已经是 RemoteSigned 、 Unrestricted 或 Bypass ，则可能无需更改执行策略。这些策略应该允许 Shell 集成正常工作。
如果输出是 Restricted 或 AllSigned ，则可能需要更改策略以启用 shell 集成。

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

## 查找配置文件
New-Item -Path $PROFILE -ItemType File -Force

notepad C:\Users\$env:USERNAME\Documents\PowerShell\Microsoft.PowerShell_profile.ps1

if ($env:TERM_PROGRAM -eq "vscode") { 
    . "$(code --locate-shell-integration-path pwsh)" 
}

## vscode中设置 PowerShell为默认终端