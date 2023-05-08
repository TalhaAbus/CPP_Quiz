```CPP
#include <iostream>

int j = 1;

int main()
{
	int& i = j, j;
	j = 2;

	std::cout << i << j;
}
```
**Çıktı:**
```
12
```
**Analiz:**
- Buradaki virgül bir operatör değil. Bu comma seperated list için kullnaılan virgül. Bu ifade parantez içine alınsaydı (j,j) o zaman operatör virgül olurdu. 
- Burada i referansı, local değişken olan j'ye değil, global değişken olan j'ye bağlanıyor. Alt satırda j = 2 dediğimizde ise namelookup kurallarına göre local j kullnaılıyor.















