```CPP
#include <iostream>

int main()
{
	char* a = const_cast<char*>("Hello");
	a[4] = '\0';
	std::cout << a;
}
```
**Çıktı:**
- Boş, Tanımsız davranış

**Analiz:**
- Const bir nesnenin değiştirilme girişimi her zaman tanımsız davranıştır.
- "Hello" nun türü C dilinde char* C++ dilinde const char* 





