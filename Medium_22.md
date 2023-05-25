```CPP
#include <iostream>

struct X {
	X() { std::cout << "a"; }
	X(const X& x) { std::cout << "b"; }
	const X& operator=(const X& x) {
		std::cout << "c";
		return *this;
	}
};

int main()
{
	X x;
	X y(x);
	X z = y;
	z = x;
}
```
**Çıktı:**
```
abbc
```
**Analiz:**
- x default init edildiği için default constructor çağırıldı.
- y direct init edildi ama ilk değer veren ifade aynı sınıf türünden olduğu için copy onstructor çağırıldı.
- z de yine copy ctor çağırıldı.




