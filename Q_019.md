```CPP
#include <iostream>

int f(int& a, int& b)
{
	a = 3;
	b = 4;
	return a + b;
}

int main()
{
	int a = 1;
	int b = 2;
	int c = f(a, a);
	std::cout << a << b << c;
}
```
**Çıktı:**
```
428
```
**Analiz:**
- Fonksiyonun 2 parametresi var ama ben ikisine de a nesnesini geçtim. Dolayısıyla buraki a ve b, main'deki a'ya referans. Yani a'yı veya b'yi değiştirsem de main deki a'yı değiştirmiş oluyorum.
- return ifadesinin değeri 8 olacak. 













