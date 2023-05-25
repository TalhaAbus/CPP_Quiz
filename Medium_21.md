```CPP
#include <iostream>

int foo()
{
	return 10;
}

struct foobar
{
	static int x;
	static int foo()
	{
		return 11;
	}
};

int foobar::x = foo();

int main()
{
	std::cout << foobar::x;
}
```
**Çıktı:**
```
11
```
**Analiz:**
- Sınıfın static veri elemanıın tanımında ilk değer veren ifadedeki isimler önce class scope ta aranıyor. Class ta bulunamazsa namespace scope ta aranıyor. Foo ismi class scope ta arandığı için bulundu ve değeri 11 oldu.
- ::foo() yazsaydım global fonksiyonun geri dönüş değeri ile ilk değer vermiş olutdum.



