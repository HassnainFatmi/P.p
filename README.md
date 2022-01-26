//take an array from the user using pointers, then take a int from the user using pointers
// Pass these pointers to a functions which checks whether the input int is in the array or not
#include <iostream>
using namespace std;
int const MAX = 50;
bool search(int* array, int* ele, int len);
int main()
{
		char op = 'y';
		int intarr[MAX], length;
		cout << "Enter the length : ";
		cin >> length;
		cout << "Enter the array : ";
		for (int i = 0; i < length; i++)
		{
			cin >> *(intarr + i);       //syntax for accessing members of an array using pointer *(arrayname+i)
		}
		do
		{
		int eleptr;
		cout << "Enter the number you want to find : ";
		cin >> eleptr;
		if (search(intarr, &eleptr, length) == 0)
		{
			cout << "No record found.\n";
		}
		else
		{
			cout << "Record found.\n";
		}
		cout << "Do you want to continue(y/n).\n";
		cin >> op;
	} while (op == 'y');
	
}
bool search(int* array, int* ele, int len)
{
	bool flag = 0;
	for (int i = 0; i < len; i++)
	{
		if (*(array+i) == *ele)
		{
			flag = 1;
			break;
		}
	}
	return flag;
}
