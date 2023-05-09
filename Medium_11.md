```CPP
#include <iostream>

struct A {
	virtual void foo(int a = 1)
	{
		std::cout << "A" << "a";
	}
};

struct B : A {
	virtual void foo(int a = 2)
	{
		std::cout << "B" << a;
	}
};

int main()
{
	A* b = new B;
	b->foo();
}
```
**Çıktı:**
```
B1
```
**Analiz:**
- Varsayılan argüman, statik türe ilişkinidir. Yani virtual dispath mekanizması ile alakası yok. foo ismi A sınıfında aranıyor. VArsayılan argüman 1. Doalyısıyla overriding mekanizmasından bağımsız olarak derleyici statik olarak koda bakıyor ve bu kodu foo(1) olarak dönüştürüyor. 
- b->foo dediğimizde çağrı taban sınıf pointerı ile ypaıldığı için virtual dispatch mekanizamsı devreye girecek ve B sınıfının fonksiyonu çağırılacak. 







