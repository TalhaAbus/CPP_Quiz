```CPP
#include <iostream>
#include <type_traits>

int main()
{
	if (std::is_signed<char>::value) {
		std::cout << std::is_same<char, signed char>::value;
	}
	else {
		std::cout << std::is_same<char, unsigned char>::value;
	}
}
```
**Çıktı:**
```
0
```
- Derleyiciye bağlı bir durum var. Derleyiciye bağlı olan durum, burada if'in doğru veya yanlış kısmına girmesini sağlayacak. Fakat ekrana yazılacak değer derleyiciye bağlı değil, sonuç her türlü 0.

