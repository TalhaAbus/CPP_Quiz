```CPP
#include <iostream>

class A {
public:
	A() { std::cout << 'a'; }
	~A() { std::cout << 'A'; }
};

class B {
public:
	B() { std::cout << 'b'; }
	~B() { std::cout << 'B'; }
	A a;
};
int main()
{
	B b;
}
```
**Çıktı:**
```
abBA
```
**Analiz:**
- B sınıfı composition ilişkisi ile bir veri elemanı almış (A sınıfı türünden). Yani bir B nsnesini hayata getirdiğimizde öncelikle, progrmaın akışı öncelikle B'nin constructor'ının ana bloğuna girmeden, eleman olan a nesnesi hayata gelecek.


