## 下载安装
见`github`：https://github.com/gabime/spdlog。需要`cmake`，`cmake`安装见：https://cmake.org/download/。
## cmake 配置

```cmake
set(CMAKE_PREFIX_PATH  
        "xxxx"  
        "D:/spdlog/build"
        "xxxxx"
)

find_package(spdlog REQUIRED) # 新增一行

target_link_libraries(  
        QGobang  
        xxxxxx  
        spdlog::spdlog $<$<BOOL:${MINGW}>:ws2_32>
        xxxxxx  
)
```
## 用法
```C++
#include "spdlog/spdlog.h"

int main() 
{
	// 六种日志级别 trace debug info warn error critical
    spdlog::trace("Welcome to spdlog!");
    spdlog::debug("Some error message with arg: {}", 1);
    spdlog::info("Easy padding in numbers like {:08d}", 12);
    spdlog::warn("Support for int: {0:d};  hex: {0:x};  oct: {0:o}; bin: {0:b}", 42);
    spdlog::error("Support for floats {:03.2f}", 1.23456);
    spdlog::critical("Positional args are {1} {0}..", "too", "supported");
    // 设置日志级别 
    spdlog::set_level(spdlog::level::debug); // Set *global* log level to debug
    // 修改日志模板
    spdlog::set_pattern("[%H:%M:%S %z] [%n] [%^---%L---%$] [thread %t] %v");
}

```
