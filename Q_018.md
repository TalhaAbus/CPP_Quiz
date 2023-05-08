```
#include <iostream>

class A {
public:
	void f() { std::cout << "A"; }
};

class B : public A{
public:
	void f() { std::cout << "B"; }
};

void g(A& a) { a.f(); }

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
**Analiz:**
- Name lookup. g fonksiyonua b nesnesi gönderilmiş. İsim arama kurallarına göre a.f() dediğimizde isim taban sınıfta aranacak ve A sınıfının fonskiyonu çağırılacak. 
- Eğer fonskiyon virtual olsaydı B çağırılırdı.














