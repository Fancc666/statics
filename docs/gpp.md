# g++指南

使用g++编译cpp文件产生的问题如下。

## C++11特性编译警告

比如新语法

```cpp
#include <iostream>
using namespace std;
int main(){
    for (int i : a){
        cout << i << endl;
    }
    return 0;
}
```
编译时添加参数`-std=c++11`解决。

## 中文乱码（Windows）

原因是，文件使用`UTF-8`编码，而Windows控制台是`GBK`，解决问题需要修改编译参数。

添加`-finput-charset=UTF-8 -fexec-charset=GBK`。

## 缺少动态链接库

将`dll`链接进`exe`文件即可，添加参数`-static-libgcc -static-libstdc++`。