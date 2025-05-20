# cline环境配置指南

## 安装 PowerShell7
```powershell
winget install --id Microsoft.PowerShell
```

管理员权限运行PowerShell执行：
```powershell
Get-ExecutionPolicy
```
如果输出已经是 RemoteSigned、Unrestricted 或 Bypass，则无需更改执行策略。  
如果输出是 Restricted 或 AllSigned，则需要执行：
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## 查找配置文件
```powershell
New-Item -Path $PROFILE -ItemType File -Force
notepad C:\Users\$env:USERNAME\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

## 添加vscode集成配置
```powershell
if ($env:TERM_PROGRAM -eq "vscode") { 
    . "$(code --locate-shell-integration-path pwsh)" 
}
```

## 设置默认终端
在vscode中按Ctrl+Shift+P打开命令面板，输入"Terminal: Select Default Profile"，选择PowerShell 7
