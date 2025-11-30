```
#include <iostream>
using namespace std;

void B() {
    cout << "called B" << endl;
}

void C() {
    cout << "called C" << endl;
}

void A() {
    cout << "called A" << endl;
    B(); 
    C();
}

int main() {
    cout << "Hello" << endl;
    A();
    int i = 69;
    int number = 72;
    i = i + number; // теперь i == 141
    int arr[3] = {0, 0, 0};
    int* iPointer = &i;
    number = *iPointer; // number = значение i (141)
    *iPointer = 15; // теперь i == 15
    iPointer = &arr[0]; // iPointer указывает на arr[0]
    iPointer += 2; // теперь iPointer указывает на arr[2] (третий элемент)
    arr[0] = 5;
    *iPointer = 6;
    cout << "i = " << i << endl;
    cout << "number = " << number << endl;
    cout << "arr[0] = " << arr[0] << endl;
    cout << "arr[1] = " << arr[1] << endl;
    cout << "arr[2] = " << arr[2] << endl;

    return 0;
}
```
