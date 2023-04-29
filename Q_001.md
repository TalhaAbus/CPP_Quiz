
```CPP
#include <iostream>

int main()
{
	static int a;
	std::cout << a;
}
```
**Analiz:**
- C++ dilinde statik ömürlü nesneler, yani global değişkenler ve statik yerel değişkenler default initializer edilirlerse, zero initialize ediliyorlar
