This code maintains the fast mass spring (http://tiantianliu.cn/) of tiantian liu 2013(original name: liu13fast, original code:http://tiantianliu.cn/papers/liu13fast/liu13fast.zip), adds cmake, and updates Eigen. The test is compiled under win10 vs2022 + cmake.

Compile method:
Download VS2022 and install the C++ desktop development environment
Download cmake and install it

Compile with cmake:
```
cmake -B build
cmake --build build
```

Copy the main.exe file in the Release directory under the Build directory to the fast_mass_spring directory, and then run it.



将tiantian liu 2013的fast mass spring( http://tiantianliu.cn/ ) 维护了一下，新增了cmake，并更新了Eigen。测试在win10 vs2022 + cmake 下通过编译。原本的源代码为：http://tiantianliu.cn/papers/liu13fast/liu13fast.zip

编译方法：
下载VS2022并且安装好C++ desktop开发环境
下载cmake并且安装好

使用cmake编译：
```
cmake -B build
cmake --build build
```

将Build目录下的Release目录下的main.exe文件拷贝到fast_mass_spring目录下，然后运行即可。
