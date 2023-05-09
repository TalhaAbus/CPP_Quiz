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
**Analiz:**
- is_pointer_v aslında bir variable template. Yani şununla aynı anlama geliyor:
```CPP
#include <iostream>
#include <cstddef>
#include <type_traits>

int main()
{
	std::cout << std::is_pointer<decltype(nullptr)>::value;
}
```
- Burada kullanılan sentaks aracı variable template. 
- Nullptr'nin ait olduğu tür, pointer türü değildir. Bu pointer'a dönüşebnilen bir class type. Yani ekrana yazdırılacak değer 0.







