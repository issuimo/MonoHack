> 2023/11/12
> 已停止更新, 请期待后续的 UnityResolve 库

# 特点
- 轻便小巧: 只需包含一个头文件即可使用
- 无缝衔接: 内置C#部分类的C++定义
- 功能强大: 涵盖 类 类型 函数 域 程序集 变量 等操作

# 待完成的Unity类型
- [X] Camera
- [X] Transform
- [ ] GameObject
- [X] Component
- [ ] LayerMask
- [ ] Rigidbody
- [X] Vector4
- [X] Quaternion
- [X] Bounds
- [X] Plane
- [X] Ray
- [X] Rect
- [X] Color
- [X] Matrix4x4

# 如何使用
> [!NOTE]\
> il2cpp使用的是 崩坏：星穹铁道 (StarRail) GameAssembly.dll导出函数列表，不同版本的Unity不同游戏导出列表略有差异\
> 部分特殊处理过的il2cpp无法使用 如: 原神 (Genshin Impact)

> [!IMPORTANT]\
> 使用示范
> ### Mono 
> - [ravenfield](https://github.com/issuimo/ravenfield)
> ### il2cpp
> - [Phasmophobia](https://github.com/issuimo/PhasmophobiaCheat)

- 引入头文件
``` c++
#include "UnityHack.h"
```

- 初始化dll地址
``` c++
// 初始化Mono
unity::Mono::SetModule(GetModuleHandleA("mono-2.0-bdwgc.dll"));

// 初始化il2cpp
unity::Il2cpp::SetModule(GetModuleHandleA("GameAssembly.dll"));
```

- 获取函数地址
``` c++
// Mono
unity::Mono::Method::GetAddress("Actor", "Awake");

// Il2cpp
unity::Il2cpp::Method::GetAddress("Actor", "Awake");
```
