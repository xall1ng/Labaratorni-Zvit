### Лабараторна робота №2
## Завдання 1. озробити програму, дотримаючись таких вимог: використовувати статичні масиви; максимальні розміри масиву (N i M) – статичні константи; реальні розміри  масиву n  i  m (n<N, m<M) – ввести з клавіатури (при цьому здійснювати перевірку правильності введення даних); елементи масиву – псевдовипадкові числа, згенеровані на інтервалі [a, b], де a і b (a<b) вводяться з клавіатури; усі вхідні дані і також елементи масиву виводити на екран. Реалізувати програму, яка сумує елементи рядків двовимірного масиву і заносить результат в одновимірний масив, розмірність якого дорівнює числу рядків двовимірного масиву.
# C++
```c++
#include <iostream>

using namespace std;

int main()
{
    int N = 1000, M = 1000, n, m, a, b, i, j;
    int A[N][M];
    int sum[N];
    
    do{
        cout<<"Введіть n"<<endl;
        cin>>n;
        cout<<"Введіть m"<<endl;
        cin>>m;
        cout<<"Введіть a"<<endl;
        cin>>a;
        cout<<"Введіть b"<<endl;
        cin>>b;
        
    }
    while(a>b && n>N && m>M);
    
    for (i = 0; i<n; i++){
        for (j = 0; j<m; j++){
            A[i][j] = a + rand()%(b-a+1);
            cout<<A[i][j]<<" ";
            
        }
        cout<<endl;
    }
    
    for (int i = 0; i < n; i++) {
        sum[i] = 0;
        for (int j = 0; j < m; j++) {
            sum[i] += A[i][j];
        }
    }
    
    cout << "Суми елементів рядків:"<<endl;
    for (int i = 0; i < n; i++) {
        cout << sum[i] << " ";
    }
    cout << endl;
    
    return 0;
}
```
# Робота програми
```console
Введіть n
5
Введіть m
5
Введіть a
10
Введіть b
20
16 20 16 12 11 
14 10 16 13 11 
18 17 15 13 17 
14 19 20 12 10 
20 18 15 10 14 
Суми елементів рядків:
75 64 80 75 77 
```
