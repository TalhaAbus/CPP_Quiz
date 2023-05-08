```CPP
#include <iostream>
#include <utility>

struct X {
	X() { std::cout << "1"; }
	X(X&) { std::cout << "2"; }
	X(const X&) { std::cout << "3"; }
	X(X&&) { std::cout << "4"; }
	~X() { std::cout << "5"; }
};

struct Y {
	mutable X x;
	Y() = default;
	Y(const Y&) = default;
};

int main()
{
	Y y1;
	Y y2 = std::move(y1);
}
```
**Çıktı:**
```
1255
```
**Analiz:**
- 2. satırda move var. Move bir tür dönüştürme fonksiyonundan başka bir şey değil. Yani y1 ifadesi L value expression iken move'un geri dönüş değeri R value expression. Yani biz y2'ye R value expression ile ilk değer vermiş oluyoruz. 
- Fakat y sınıfının move constructor'ı yok. Copy constructor çağırılacak. Y'nin copy constructor'ı derleyici tarafından yazılmış. Bu copy constructor, Y'nin elemanı olan mutable x'i copy construct edecek. 
- Eğer x mutable olmasaydı, dil kurallarına göre 3 değerini yazdıran copy constructor çağırılacaktı. Ama x mutable olunca 2 yazdıran copy constructor'ın seçilebilirliği daha yüksek oluyor. 










