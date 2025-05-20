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

[CLI环境配置指南](cline.md)
