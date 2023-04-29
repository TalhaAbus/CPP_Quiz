```CPP
#include <iostream>

void f(char*&&) { std::cout << 1; }
void f(char*&) { std::cout << 2; }

int main()
{
	char c = 'a';
	f(&c);
}
```
**Çıktı:**
```
1
```
- Burada T&& ve T& overloading var.  Üstteki fonksiyonun parametresi sağ taraf referansı, alttaki sol taraf referansı. Derleyici function overload resolution'da gönderdiğimiz ifadenin değer kategorisi kullanacak.
- & operatörü ile oluşturulan ifadenin değer kategorisi PR value expression. 
