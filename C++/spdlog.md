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
    spdlog::info("Welcome to spdlog!");
    spdlog::error("Some error message with arg: {}", 1);
    
    spdlog::warn("Easy padding in numbers like {:08d}", 12);
    spdlog::critical("Support for int: {0:d};  hex: {0:x};  oct: {0:o}; bin: {0:b}", 42);
    spdlog::info("Support for floats {:03.2f}", 1.23456);
    spdlog::info("Positional args are {1} {0}..", "too", "supported");
    spdlog::info("{:<30}", "left aligned");
    
    spdlog::set_level(spdlog::level::debug); // Set *global* log level to debug
    spdlog::debug("This message should be displayed..");    
    
    // change log pattern
    spdlog::set_pattern("[%H:%M:%S %z] [%n] [%^---%L---%$] [thread %t] %v");
    
    // Compile time log levels
    // Note that this does not change the current log level, it will only
    // remove (depending on SPDLOG_ACTIVE_LEVEL) the call on the release code.
    SPDLOG_TRACE("Some trace message with param {}", 42);
    SPDLOG_DEBUG("Some debug message");
}

```
