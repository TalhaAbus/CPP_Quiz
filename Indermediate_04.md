```CPP
#include <iostream>
#include <type_traits>

int main()
{
	std::cout << std::is_signed<char>::value;
}
```
**Çıktı:**
```
1
```
**Analiz:**
- Bu sorunun cevabı implementation defined. char türünün signed olması durumu derleyiciye bağlı.
