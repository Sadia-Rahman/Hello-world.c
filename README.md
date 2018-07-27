#include<iostream>
using namespace std;

///Class declaration
class obj1;
class obj2;
class obj3;

class obj1
{
    float r1;
public:
    void get(){cin>>r1;}
    friend float largest (obj1,obj2,obj3);
};

class obj2
{
    float r2;
public:
    void get(){cin>>r2;}
    friend float largest (obj1,obj2,obj3);
};

class obj3
{
    float r3;
public:
    void get(){cin>>r3;}
    friend float largest (obj1,obj2,obj3);
};

float largest (obj1 a,obj2 b,obj3 c)
{
    if(a.r1>b.r2 && a.r1>c.r3)
        return a.r1;
    else if(b.r2>a.r1 && b.r2>c.r3)
        return b.r2;
    else if(c.r3>a.r1 && c.r3>b.r2)
        return c.r3;
}

int main()
{
    obj1 x;
    obj2 y;
    obj3 z;
    x.get();
    y.get();
    z.get();

    float m;
    m=largest(x,y,z);
    cout<<"\nThe largest radius is:"<<m<<endl;
    return 0;
}

