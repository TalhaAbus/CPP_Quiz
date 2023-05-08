```CPP
#include <iostream>

class A {
	int foo = 0;
public:
	int& getFoo() { return foo; }
	void printFoo() { std::cout << foo;}
};

int main()
{
	A a;

	auto bar = a.getFoo();
	++bar;
	a.printFoo();
}

```
**Çıktı**
```CPP
0
```
**Analiz:**
> A Sınıfı türünden bir nesne tanımlandı Default init edildi. getFoo nun geri dönüş türü referans. Ama auto da referans declerator ü yok. Dolayısıyla fonksiyonun geri dönüş türü referans olmasına rağmen bar değişkeni referans değil, int türünden. Yani bar değişkeni ınıfın veri elemanına referans değil. Yani bar değişkeni 1 arttırıldığında eleman 1 artmıyor. Ama auto& olsaydı cevap 1 olurdu.
