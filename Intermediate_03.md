```CPP
#include <iostream>

struct S {
	int one;
	int two;
	int three;
};

int main()
{
	S s{ 1,2 };
	std::cout << s.one;
}
```
**Çıktı:**
```
1
```
**Analiz:**
- Eğer initializer sayısı yapıdaki öge sayısından daha az ise, init edilmeyen ögeler doğrudan 0 değeri ile hayata başlıyorlar.
- 



