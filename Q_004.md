```CPP
#include <iostream>

int main()
{
	int a = 10;
	int b = 20;
	int x;
	x = a, b;
	std::cout << x;
}
```
- Operatör önceliği. Atama operatörü daha yüksek öncelikli. İfade parantez içine alınsaydı ((a,b)) cevap 20 olacaktı.
