```CPP
#include <iostream>

class C {
public:
	C(int i) : i(i) { std::cout << i; }
	~C() { std::cout << i + 5; }
private:
	int i;
};

int main()
{
	const C& c = C(1);
	C(2);
	C(3);
}
```
**Çıktı:**
```
127386
```
**Analiz:**
- İlk önce geçici nesne için sınıfın int parametreli constructor'ı çağırılacak. 
- Referansa bağlandığında life expansion gerçekleşiyor. Aslında geçici nesneler onları içeren ifadelerin değerlendirilmesinden sonra hayatı bitiyor. Ama eğer bu geçici nesneyi bir referansa bağlarsak artık bu nesnenin hayatı referans olan ismin scope'unun solunda hayatı bitecek. Yani ilk C'nin hayatı main sonunda bitecek.

**Kod böyle olsaydı:**
```CPP
#include <iostream>

class C {
public:
	C(int i) : i(i) { std::cout << i; }
	~C() { std::cout << i + 5; }
private:
	int i;
};

int main()
{
	{
		const C& c = C(1);
		C(2);
	}
	C(3);
}
```
Çıktı:
```
127638
```





