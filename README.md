#include <iostream>
using namespace std;
int quic_short(int arr[],int i,int n) 
{
	int loc=i;
	while(i<n)
	{
		if(arr[i]<arr[n])
		{	
		swap(arr[loc],arr[i]);
		loc++;
	    }
	    i++;

	}
	swap(arr[loc],arr[n]);
	return loc;
}
int part(int arr[],int i,int n)
{
  if (i<n)
  {
  int pivot=quic_short(arr,i,n);
  part( arr,i,pivot-1);
  part(arr,pivot+1,n);

  }
}
void display(int arr[],int n)
{    cout<<"\n********displaying array********\n";
	for (int i = 0; i < n; ++i)
	{
		cout<<arr[i]<<"\t";
	}
}
int create(int arr[],int n)
{
	for (int i = 0; i < n; ++i)
	{   cout<<"\nentere the value of arr["<<i<<"]\t";
		cin>>arr[i];
	}
}
int main()
{
	int arr[]={1,3,2,6,4,9,0};
	int option;
	int n;
	while(1)
	{  
		cout<<"\n******enter your option*******\t";
		cout<<"\n 1:create array\n 2:quic_short\n 3:display\n ******ctrl Z for break the program******\t";
		cin>>option;
		switch(option)
		{
			case 1:cout<<"\n enter the size of array\t";
			       cin>>n;

			     create(arr,n);
			     break;
			case 2:part(arr,0,n-1);
			     break;
			case 3:display(arr,n);
			     break;
			default :cout<<"please enter the correct option";     

		}
	}

	//int n=sizeof(arr)/sizeof(arr[0]);

	//part(arr,0,n);
	//display(arr,n);

}
