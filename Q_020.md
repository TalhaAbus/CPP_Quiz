```CPP
#include <iostream>

class A {
public:
	virtual void f() { std::cout << "A"; }
};

class B : public A {
private:
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
B
```
**Analiz:**
- B sınıfı türünde bir neesne tanımlanmış ve g fonksiyonu çağırılmış. 
- Burada B sınıfının f fonksiyonu private. Dolayısıyla global g fonksiyonuna b nesnesini gönderdiğim zaman sanallık mekanizması devreye giriyor. Private olması durumunda sanallık mekanizması devreye girmeyecekmiş gibi gelebilir. Oysa public ya da private olması runtime'a yönelik değildir.
- Yani A sınıfında f fonksiyonu private olsaydı sentaks hatası olcaktı.




