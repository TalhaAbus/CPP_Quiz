```CPP
#include <iostream>

int main()
{
	std::cout << sizeof("");
}
```
**Çıktı:**
```
1
```
- String literalleri, const char dizilerdir. Bu dizinin türü const char[1]. Çünkü null karakter var. Cevap 1.

