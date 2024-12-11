#include<iostream>
using namespace std;
class complex
{
private:
int x,y;
public:
complex() //default constructor
{
x=0;
y=0;
}
complex(int real,int img) //parameterized constructor
{
x=real;
y=img;
}
complex operator+(complex c) //+ operator overloading
{
complex temp;
temp.x=x+c.x;
temp.y=y+c.y;
return temp;
}
complex operator*(complex c) //* operator overloading
{
complex temp;
temp.x=(x*c.x)-(y*c.y);
temp.y=(y*c.x)+(x*c.y);
return temp;

}
friend istream &operator>>(istream &,complex &); //friend function with >>,<< operator overloading

friend ostream &operator<<(ostream &,complex &);
};
istream &operator>>(istream &a,complex &c)
{
a>>c.x>>c.y;
return a;
}
ostream &operator<<(ostream &k,complex &c)
{
k<<c.x<<"+"<<c.y<<"i";
return k;
}
int main()
{
complex c1; //default constructor with 0+0i
cout<<c1<<endl;
complex c2(2,5); //parameterized constructor
cout<<c2<<endl;
complex c3; //take user defined 1st complex number
cout<<"enter the first comp no";
cin>>c3;
complex c4; //take user defined 2nd complex number
cout<<"\nenter the sec comp no";
cin>>c4;
complex c5;
cout <<"\nadd is";
c5=c3+c4; //Call +operator overloading
cout<<c5<<endl;

cout<<"mul is";
c5=c3*c4; //Call *operator overloading
cout<<c5<<endl;
return 0;
}
