# Лабораторная работа 2

## 2.1  Структуры

```cpp
#include <string.h>
#include <iostream>

struct TwoInts
{
    int a;
    int b;
};

struct StructWithArray
{
    int arr[4];
    int* someNumber;
};

int main()
{
    TwoInts i2 = { };
    i2.a = 5;
    i2.b = 7;

    std::cout << i2.a << std::endl; //выводится 5
    std::cout << i2.b << std::endl; //выводится 7
    
    StructWithArray s = { };
    s.arr[0] = 10; //записывается 10 на 0 индекс в массиве

    StructWithArray s1 = { };
    s1.arr[0] = 15; //записывается 15 на 0 индекс в массиве

    StructWithArray* sPointer = &s;
    sPointer->arr[0] = 20; //sPointer->arr[0] эквивалент (*sPointer).arr[0], перезаписывается 20 на 0 индекс в массиве

    std::cout << s.arr[0] << std::endl; //выводится 20
    s.arr[0] = 25; //перезапись на 25
    std::cout << s.arr[0] << std::endl; //выводится 25
    sPointer->arr[0] = 30; //перезапись на 30
    std::cout << s.arr[0] << std::endl; //выводится 30

    sPointer = &s1; //ссылка на ячейку s1
    sPointer->arr[0] = 35; //разименование ссылки и перезапись на 35
    std::cout << s.arr[0] << std::endl; //выводится 30
    std::cout << s1.arr[0] << std::endl; //выводится 35

    StructWithArray structArray[2] = { }; //создается массив
    structArray[0].arr[3] = 77; //на 0 индекс в structArray записывается число 77
    structArray[1].someNumber = &structArray[0].arr[3]; //ссылка на structArray[0].arr[3] = 77;

    sPointer = &s; //снова указывает на s
    int* pointer = &sPointer->arr[3]; //это адрес s.arr[3] 
    s.arr[3] = 72;
    std::cout << *pointer; // выводится 72

    StructWithArray memory;
    memset(&memory, 0, sizeof(StructWithArray)); //memset заполняет все байты объекта нулями
    //&memory - адрес структуры, 0 - байт, которым заполняем объекты, sizeof(StructWithArray) - сколько байт нужно заполнить
    return 0;
}
```  
  
  
## 2.2 Функции

```cpp
#include <iostream>

struct Prices {
    int drink;
    int first;
    int second; 
};

struct Choises {
    int drink;  
    int first;
    int second;
};

int customerTotal(Prices p, Choices c) {
    return (c.drink * p.drink)
           (c.first * p.first)
           (c.second * p.second)
}

int main() {
    Prices prices = {10, 20, 30};
    {
        Choises choises = {100, 0, 250};
        int total = customerTotal(prices, choises);
        std::cout << "Клиент 1: " << total << " лей"; 
    }

    {
        Choises choises = {0, 300, 0};
        int total = customerTotal(prices, choises);
        std::cout << "Клиент 2: " << total << " лей";
    }

    return 0;
}
```
