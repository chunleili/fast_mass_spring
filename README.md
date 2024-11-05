This code maintains the fast mass spring (http://tiantianliu.cn/) of tiantian liu 2013(original name: liu13fast, original code:http://tiantianliu.cn/papers/liu13fast/liu13fast.zip), adds cmake, and updates Eigen. The test is compiled under win10 vs2022 + cmake.

Compile method:
Download VS2022 and install the C++ desktop development environment
Download cmake and install it
Install cmake tool plug-in for vscode

Compile with cmake:
```
cmake -B build
cmake --build build
```

Run:
```
cd fast_mass_spring
./main.exe
```



# Chinese
将tiantian liu 2013的fast mass spring( http://tiantianliu.cn/ ) 维护了一下，新增了cmake，并更新了Eigen。测试在win10 vs2022 + cmake 下通过编译。原本的源代码为：http://tiantianliu.cn/papers/liu13fast/liu13fast.zip

编译方法：
下载VS2022并且安装好C++ desktop开发环境
下载cmake并且安装好
安装vscode的cmake工具插件

使用cmake编译：
```
cmake -B build
cmake --build build
```

运行
```
cd fast_mass_spring
./main.exe
```

----
## How to Debug(Windows 10 + vscode)

.vscode/launch.json
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(msvc) Launch",
            "type": "cppvsdbg",
            "request": "launch",
            // Resolved by CMake Tools:
            "program": "${workspaceFolder}/fast_mass_spring/main.exe",
            "args": [],
            "stopAtEntry": true,
            "cwd": "${workspaceFolder}/fast_mass_spring",
            "environment": [
                {
                    "name": "PATH",
                    "value": "${env:PATH}:${command:cmake.getLaunchTargetDirectory}"
                }
            ],
        }
    ]
}
```
F5 to debug.