```CPP
#include <iostream>

int i;

void f(int x)
{
	std::cout << x << i;
}

int main()
{
	i = 3;
	f(i++);
}
```
**Çıktı:**
```
34
```
**Analiz:**
- Fonksiyona 3 değerini gönderdik. i++ dan sonra yan etki kendini gerçekleştirmiş durumda. Dolayısıyla burada i'nin değeri 4 olarak yazdırılacak. Bu sequencing ile ilgili bir soru.




