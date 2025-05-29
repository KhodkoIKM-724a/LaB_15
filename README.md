#include <iostream>
#include <vector>
#include <algorithm>
#include <ctime>
#include <cstdlib>
#include <locale>
#include <windows.h>

int main() {

    system("chcp 65001 > nul");
    setlocale(LC_ALL, "");

    const int SIZE = 20;
    int a[SIZE];

    std::srand(static_cast<unsigned int>(std::time(nullptr)));

    std::wcout << L"Масив a:\n";
    for (int i = 0; i < SIZE; ++i) {
        a[i] = std::rand() % 101 - 50; // [-50; 50]
        std::wcout << a[i] << L" ";
    }
    std::wcout << std::endl;

    std::vector<int> b;
    for (int i = 0; i < SIZE; ++i) {
        if (a[i] < 0)
            b.push_back(a[i]);
    }

    std::sort(b.begin(), b.end());

    std::wcout << L"\nВід’ємні елементи масиву a (відсортовані):\n";
    for (int x : b)
        std::wcout << x << L" ";
    std::wcout << std::endl;

    return 0;
}
