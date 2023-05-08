```CPP
#include <iostream>

struct GeneralException {
	virtual void print() { std::cout << "G"; }
};

struct SpecialException : public GeneralException {
	void print()override { std::cout << "S"; }
};

void f() {	throw SpecialException(); }

int main() {
	try {
		f();
	}
	catch (GeneralException e) {
		e.print();
	}
}
```
**Çıktı:**
```
G
```
- Referans semantiği ile değil, kopyalama semantiği ile catch yazılmış Object slicing var. Yani virtual dispatch mekanizması devreye girmiyor. Referans oılsaydı object slicing olmayacaktı ve S yazacaktı.
- 
