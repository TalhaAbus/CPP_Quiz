```CPP
#include <iostream>

struct A {
	A() { foo(); }
	virtual ~A() { foo(); }
	virtual void foo() { std::cout << "1"; }
	void bar() { foo(); }
};

struct B : public A {
	virtual void foo() { std::cout << "2"; }
};

int main()
{
	B b;
	b.bar();
}
```
**Çıktı:**
```
121
```
**Analiz:**
- B sınıfı türünden b nesnesi oluşturulduğunda B'nin constructor ı çalıştı ve bu da taban sınıf olan A'nın constructor'ını çağırdı. Constructor içinde yapılan sanal fonksiyon çağrılarında sanalık mekanizması devreye girmez. Zaten virtual dispatch tetiklenseydi felaket olurdu. 
- b'nin bar fonksiyonu çağırılıyor ve bu da foo 'yu çağırıyor. Virtual dispatch devreye girefcek ve çağırılan B sınıfının foo fonksiyoınu olacak.
- b nesnesinin hayatı bittiğinde b'nin destructoır ı çağırılacak. Bu da A'nın destrcutıor'ını çağıracak. Buranın içinde sanal fonksiyon çağırısında yine destructor içinde sanal fonksiyon çağrısı virtual dispatch e bağlanmayacak.
-



