```CPP
#include <iostream>

class A {
public:
	virtual void f() { std::cout << "A"; }
};

class B : public A {
public:
	void f()  {std::cout << "B"; }
};

void g(A a) { a.f(); }

int main()
{
	B b;
	g(b);
}

```
**Çıktı:**
```
A
```

- g fonksiyonunun parametresi referans değil. Object slicing var. Sanallık mekanizması devreye girmez. Dolayısıyla çağırılan, A sınıfının f fonksiyonudur. Ben buraya B göndersem bile virtual dispatch mekanizması devreye girmeyecek ve çağırılan A sınıfının f fonksiyonu olacak. g fonksiyonunun parametresi referans olsaydı çağırılan B olacaktı.
