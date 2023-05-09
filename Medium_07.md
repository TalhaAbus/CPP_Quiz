```CPP
#include <iostream>

using namespace std;

class A {
public: 
	A() { cout << "a"; }
	~A() { cout << "Ã"; }
};

int i = 1;

int main()
{
label:
	A a;
	if (i--)
		goto label;
}
```
**Çıktı:
```
aAaA
```
**Analiz:**
- goto ile label'a geri dönünce ne olacak? Burada ilk nesne destroy olmuş durumda. Bu durumda tekrar bu nesne hayata gelcek.
