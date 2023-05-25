```CPP
#include <iostream>

void f(int a = []() {static int b = 1; return b++; }())
{
	std::cout << a;
}

int main()
{
	f();
	f();
}
```
**Çıktı:**
```
12
```
**Analiz:**
- Burada immediately invoked lambda expression var.
- lambda ifadesi, derleyiciye bir sınıf kodu yazdırır ve derleyici ifadeyi o sınıf türünden bir geçici nesneye dönüştürür. Yani aslında derleyicinin oluşturduğu geçici nesneyi fonksşiyon çağrı operatörğnün operandı yaptım.
- 2. fonksiyon çağrısında varsayılan argühan hala 1 mi yoksa 2 mi?
- Varsayılan argüman olan ifade her fonksiyon çağrısında ayrıca evaluate ediliyor. 
