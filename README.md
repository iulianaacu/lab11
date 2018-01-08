# lab11#include <iostream>

#include <vector>

using namespace std;

template <typename T>
class Stack
{
private:
    vector <T> v;
    T ultimul;

public:
    bool empty()
    {
        return v.size() == 0;
    }

    void push(const T &item)
    {
        v.push_back(item);
        ultimul = item;
    }

    T& top()
    {
        return ultimul;
    }

    void pop()
    {
        if((*this).empty() == true)
        {
            cout<<"Eroare: Stiva este goala"<<endl;
            return;
        }
        v.pop_back();
        ultimul = v[v.size()-1];
    }
};

int main()
{
    Stack <int> stiva;
    cout<<"Stiva este goala?"<<endl;
    cout<<stiva.empty()<<endl;
    stiva.push(3); //adauga item in stiva
    stiva.push(9);
    cout<<"Stiva este goala"<<endl;
    cout<<stiva.empty()<<endl;
    cout<<"Cel mai recent item adugat?"<<endl;
    cout<<stiva.top()<<endl;
    stiva.pop();//scoate din stiva cel mai recent item adugat
    return 0;
}
