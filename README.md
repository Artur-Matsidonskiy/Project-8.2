# Project-8.2
#include <iostream>
#include <math.h>
using namespace std;

void func1( )
{
    int mas1[10];
    for (int i = 0; i < 10; i++)
    {
        mas1[i] = rand() % 100;
        cout << mas1[i] << " ";
        if (i == 9) { cout << endl; }
    }
}
void func2()
{
    int mas2[5];
    for (int i = 0; i < 5; i++)
    {
        mas2[i] = rand() % 100;
        cout << mas2[i] << " ";
        if (i == 4) { cout << endl; }
    }
}
void masmas()
{
    int static k = 0;
    k++;
    int static masmas[5][5];
    if(k == 1) 
    {
        for (int i = 0; i < 5; i++)
        {
            for (int ii = 0; ii < 5; ii++)
            {
                do
                {
                    masmas[i][ii] = rand() % 61;
                } while (masmas[i][ii] < 30);
                cout << masmas[i][ii] << " ";
                if (ii == 4) { cout << endl; }
            }
        }
    }
    else
    {
        int callmax, callmin;
        callmax = callmin = 0;
        int static min, max;
        for (int i = 0; i < 5; i++)
        {
            for (int ii = 0; ii < 5; ii++)
            {
                int callmax, callmin;
                callmax = callmin = 0;
                for (int iii = 0; iii < 5; iii++)
                {
                    for (int iiii = 0; iiii < 5; iiii++)
                    {
                        if (masmas[i][ii] >= masmas[iii][iiii]) { callmax++; if (callmax == 25) { max = masmas[i][ii]; }  }
                        if (masmas[i][ii] <= masmas[iii][iiii]) { callmin++; if (callmin == 25) { min = masmas[i][ii]; }  }
                    }
                }
            }
        }
        cout << "Самое большое число в этом массиве равно: " << max << "." << endl;
        cout << "Самое маленькое число в этом массиве равно: " << min << "." << endl;
    }
}
int hero()
{
    int static i;
    int static k = 0;
    k++;
    if (k == 1)
    {
        i = rand() % 2;
        return (i);
    }
    else
    {
        if (i == 0) { i++; return (i); }
        if (i == 1) { i--; return (i); }
    }
}
void doublecube(int i)
{
    int static k = 0;
    k++;
   if (k <= 8)
   {
        
        int cube1, cube2;
        do
        {
            cube1 = rand() % 6;
        } while (cube1 == 0);
        do
        {
            cube2 = rand() % 6;
        } while (cube2 == 0);
        int static sumbot = 0;
        int static sumhero = 0;
        if (i == 0)
        {        
            sumbot += (cube1 + cube2);
            int static botnum = 0;
            botnum++;
            cout << "Сейчас ходит компьютер. Компьютер кидает №" << botnum << " раз. Сумма его очков равна: " << sumbot << "." << endl;
        }
        if (i == 1)
        {           
            sumhero += (cube1 + cube2);
            int static heronum = 0;
            heronum++;
            cout << "Сейчас ваш ход. Нажмите любую цифру, что бы продолжить." << endl;
            int q;
            cin >> q;
            cout << "Вы кидаете " << heronum << " раз. Сумма ваших очков равна: " << sumhero << "." << endl;
        }
        if (k == 8) { if (sumhero > sumbot) { cout << "Герой победил! Он выграл на " << (sumhero - sumbot) << " очков." << endl; } else { cout << "Компьютер победил! Он выграл на " << (sumbot - sumhero) << " очков." << endl; } }
        doublecube(hero());
   }
   
}


int main()
{

    setlocale(LC_ALL, "Rus");
    cout << "Первая задача готова к проверке." << endl;
    cout << "Первый массив: " << endl;
    func1();
    cout << "Второй массив: " << endl;
    func2();
    cout << "Вторая задача готова к проверке. " << endl;
    cout << "Двойной массив имеет такой вид: " << endl;
    masmas();
    masmas();
    cout << "Третья задача готова к проверке. " << endl;
    doublecube(hero());
    
   
   




   
    
}
