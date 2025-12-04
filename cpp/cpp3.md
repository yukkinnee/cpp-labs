# Лабораторная работа 3

Какие тут типы, и какие тут объекты? перечислите все.
```cpp
#include <array>

struct Leg
{
    int length;
};

struct Arm
{
    int power;
};

struct Person
{
    std::array<Leg, 2> legs;
    Arm arms[2];
};

int main()
{
    Person person;
}
```  
  
**Типы:**  
Leg  
Arm  
Person  
std::array<Leg, 2>  
Arm[2]  
int  
  
**Объекты:**  
person  
person.legs  
person.legs[0]  
person.legs[1]  
person.legs[0].length  
person.legs[1].length  
person.arms[0]  
person.arms[1]  
person.arms[0].power  
person.arms[1].power  
