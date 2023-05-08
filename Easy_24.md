```CPP
#include <iostream>

int main()
{
	int i = 42;
	int j = 1;
	std::cout << i / --j;
}
```
**Çıktı:**
```
Exception
```
**Analiz:**
- Tam sayı türlerinde Sıfıra bölme işlemi undefined behaviour. -- operatörünün ürettiği değer 0 olacak. 
