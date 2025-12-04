# Лабораторная работа 4

## 4.1 bool
Примеры на понимание
## 4.2 flow control
Примеры на понимание  
  
**Рефакторинг**
```cpp
#include <iostream>

void testAndPrint (int number) {
         if (number == 5)
        {
            std::cout << "The number is 5" << std::endl;
            return;
        }
         std::cout << "The number is not 5" << std::endl;
         
        if (number % 2 == 1)
        {
            std::cout << "The number is not divisible by 2" << std::endl;
            return;
        }
         std::cout << "The number is divisible by 2" << std::endl;
         
         if (number == 6)
        {
            std::cout << "The number is 6" << std::endl;
            return;
        }
        
    }


int main()
{
    int number = 10;
    testAndPrint(number);
}
```

## 4.3 Span

```cpp
#include <iostream>
#include <span>
#include <cassert>

void productFor(std::span<int> inputOutput, std::span<int> coefficients)
{
    assert(inputOutput.size() == coefficients.size());

    for (size_t i = 0; i < inputOutput.size(); ++i) {
        inputOutput[i] *= coefficients[i];
    }
}

void productWhile(std::span<int> inputOutput, std::span<int> coefficients)
{
    assert(inputOutput.size() == coefficients.size());

    size_t i = 0;
    while (true) {
        if (i >= inputOutput.size())
        {
            break;
        }
        inputOutput[i] *= coefficients[i];
        ++i;
    }
}

int main() {
    
    std::array a{1, 2, 3};
    std::array b{4, 5, 6};
    productWhile(a, b);
    for (auto it {a.begin()}; it != a.end(); ++it) {
        int x = *it;
        std::cout << x << std::endl;
    }
}
```
