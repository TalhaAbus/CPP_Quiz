```CPP
#include <iostream>

int main()
{
	int a = 0;
	decltype((a)) b = a;
	b++;
	std::cout << a << b;
}

```
**Çıktı:**
```
11
```
- Çift parantez olmasaydı tür çıkarımı kuralı farklı olacaktı. Eğer decltype'ın operandı bir isimse elde edilen tür referans türü değildir. Ama eğer bu ifade bir isim formunda değilse ((a)) bu durumda elde edilen tür bu ifadenin değer kategorisine bağlı.
- İfade L value expression ise elde edilen tür referans türü. PR value ise elde edilen tür, türün kendisi, X value expression ise elde edilen tür sağ taraf referansı.
- Burada b, a'ya referans oldu.




