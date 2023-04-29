# h-t-01.05


#include <iostream>
using namespace std;

template <typename T>
T SearchMM(T* arr, int n)
{
    //min&max
    int min = arr[0];
    int max = arr[1];
    for (int i = 0; i < n; i++)
    {
        if (arr[i] < min)
		{
			min = arr[i];
		}
        if (arr[i] > max)
        {
			max = arr[i];
		}
    }
    cout << "\n Min element - " << min << endl;
    cout << "\n Max element - " << max << endl;
}

template <typename T>
T Sort(T* arr, int n)
{
    //sorting
    int temp; 
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
    cout << "\n Sort Array: " << endl;
    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
    return arr[n];
}

template <typename T>
T SearchE(T* arr, int n)
{
    //element search
	int ind;
	cout << "\n Eter the index of the required element - ";
	cin >> ind;
	for (int i = 0; i < n; i++)
	{
		if (ind == i)
		{
			cout << arr[i] << endl;
		}
	}
	return arr[n];
}

template <typename T>
T Replacement(T* arr, int n)
{
    int ind;
    int ch;
	cout << "\n Enter the element number - ";
	cin >> ind;
	cout << "\nEnter New Element - ";
	cin >> ch;
	for (int i = 0; i < n; i++)
	{
		if (ind == i)
		{
			arr[i] = ch;
		}
		cout << arr[i] << " ";
	}
	cout << endl;
	return 0;
}

int main()
{
    int n;
    cout << "\n Enter the number of elements - ";
    cin >> n;
    int arr[n];
    cout << "\n Input Array Elements: " << endl;
	for (int i = 0; i < n; i++)
	{
		cin >> arr[i];
	}
	cout << "\n Array: ";
	for (int i = 0; i < n; i++)
	{
		cout << arr[i] << " ";
	}
	cout << endl;
	int a = SearchMM<int>(arr, n);
	int b = Sort<int>(arr, n);
	int c = SearchE<int>(arr, n);
	int e = Replacement<int>(arr, n);
}
