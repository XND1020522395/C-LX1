# C-LX1
lianxi
#include "stdafx.h"
#include<iostream>
using namespace std;

class CTest
{
public:
	void outdata();
	void indata();
	CTest();
	CTest(CTest &ot);
private:
	int age;
};
CTest::CTest(CTest &ot)
{
	age = ot.age * 2;
	cout << "复制构造函数 age=" << age << endl;
}
void CTest::outdata()
{
	cout << "outdata()函数 age=" << age << endl;
}
void CTest::indata()
{
	cout << "intdata()函数 age=";
	cin >> age;
}
CTest::CTest()
{
	age = 100; 
	cout << "默认构造函数 age = " << age << endl;
}

int main()
{
	CTest obj;
	obj.indata();
	obj.outdata();
	CTest obj2(obj);
	obj2.outdata();
	return 0;
}
