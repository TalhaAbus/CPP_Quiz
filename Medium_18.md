```CPP
#include <iostream>

int main()
{
	std::cout << 1["ABC"];
}
```
**Çıktı:**
```
B
```
**Analiz:**
- Parantez operatörü için derleyicinin ürettii kod, dıştaki operand ve içteki operandı toplama opratörünün operandı yaptı ve bunu da dereference etti.
- 




