```CPP
#include <iostream>

class A {
public:
	A() { std::cout << "a"; }
	~A() { std::cout << "A"; }

};

class B {
public:
	B() { std::cout << "b"; }
	~B() { std::cout << "B"; }

};

class C {
public:
	C() { std::cout << "c"; }
	~C() { std::cout << "C"; }
};

A a;

int main()
{
	C c;
	B b;
}
```
**Çıktı::**
```
acbBCA
```
**Analiz:**
- Statik ömürlü nesneler, main fonksiyonunda önce hayata geliyor. (main'deki ilk fonksiyon çağrısından önce). İlk olarak A'nın constructor ı çağırıldı. C ve B'nin constructor'ı çalıştı. Ve Son hataya gelenin hayattı ilk biter.











