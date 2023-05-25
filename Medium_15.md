```CPP
#include <iostream>
#include <algorithm>

int main()
{
	int x = 10;
	int y = 10;

	const int& max = std::max(x, y);
	const int& min = std::max(x, y);

	x = 11;
	y = 9;

	std::cout << max << min;
}
```
**Çıktı:**
```
1111
```
**Analiz:**
- max ve min template leri referans döndürüyor. Yani max template in geri dönüş değeri T değil, T&.
- Değerler eşit olduğunda ne döndürüyor?
- Standartlara göre ikisi eşit ise birinciyi dönüdrmek zorunda.
- 









