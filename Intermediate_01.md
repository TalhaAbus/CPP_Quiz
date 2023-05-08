```CPP
#include <iostream>

namespace x {
	class C{};
	void f(const C& i)
	{
		std::cout << "1";
	}
}

namespace y {
	class C {};
	void f(const x:: C& i)
	{
		std::cout << "2";
	}
}

int main()
{
	f(x::C());
}
```
**Çıktı:**
```
1
```
**Analiz:**
- İsim arama kurallarına göre fonksiyon içindeki isim:
1. Normal yol ile aranacak
2. Bu isim bir namespace içinde tanımlanan bir sınıf türüne ilişkin oludğu için bu isim (f ismi), argüman olan ifade bir namespace içindeki sınıf türünden oludğu için normal arandığı yerin dışında o namespace içinde de aranacak. 
3.  



