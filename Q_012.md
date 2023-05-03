```CPP
#include <iostream>
#include <cstddef>
#include <type_traits>

int main()
{
	std::cout << std::is_pointer_v<decltype(nullptr)>;
}
```
**Çıktı:**
```
0
```
- is_pointer_v aslında bir variable template:
```CPP
std::cout << std::is_pointer<decltype(nullptr)>::value;
```
- Bu satır ile aynı anlama geliyor.
- is_pointer metafunction, template tür argümanı oalrak kullanılan türün pointer türü olup olmadığını sınamak için var.
- Burada nullptr'nin türü nullptr_t türüdür. Bu bir pointer türü değil. Bu pointer'a dönüşebilen bir class type. Yani çıktı 0.

**Pointer türünden deilse nasıl pointerlara atayabiliyoruz?**
- Kendisi pointer türü değil ama pointer türüne dönüşebiliyor.


