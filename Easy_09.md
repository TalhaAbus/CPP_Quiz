```CPP
#include <iostream>

struct A {
	A() { std::cout << "A"; }
};
struct B {
	B()  {std::cout << "B ";}
};

class C {
public:
	C() : a(), b() {}
private:
	B b;
	A a;
};

int main() {
	C();
}
```
**Çıktı:**
```
BA
```

- Constructor initializer list'teki sıra nesnelerin  hayata gelmesinde belirleyici değildir. Sınıfın tanımında elemanların bildirilme sırası belirleyicidir. 




