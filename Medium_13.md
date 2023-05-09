```CPP
#include <iostream>
#include <type_traits>

int main()
{
	std::cout << std::is_same_v<
		void(int),
		void(const int)>;
	std::cout << std::is_same_v<
		void(int*),
		void(const int*)>;
}
```
**Çıktı:**
```
10
```
**Analiz:**
- is_same trait'i en çok kullnaılan trait lerden birisi. Eğer türler aynı ise value aynı olacak farklı ise value false olacak.
- C ve C++ dillerinde cpointer olmayan parametresini const olması imzada farklılık yaratmıyor. İlk çıkış deyimi ekrana 1 yazar. İkinci yazdırılan ise farklı türler olduğundan 0 yazar.
- 



