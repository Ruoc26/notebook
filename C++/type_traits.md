### 实现泛型限制
```C++
# C++ 20
template<typename T> requires std::disjunction_v<  
        std::is_same<T, ClassOne>,  
        std::is_same<Sink, ClassTwo>  
>  
class Child : public Father {};
```