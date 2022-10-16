#include <iostream>                     
using namespace std;          

int binary_search(int arr[],int i,int j,int k){
    int m=(i+j)/2; //m=middle element
    while(i<=j){   //i=starting index j=ending index
    if(arr[m]==k){return m;}  // if key to be searched is present we will return index of the key
    else{
        if(arr[m]<k){i=m+1;}
        else{j=m-1;}
    }
    m=(i+j)/2;
    }
    return -1;  
}

int binary_search_unknown(int arr[],int k){
    int i=0,j=1;
    //We will increase j until arr[j] exceeds key to be searched.
    while(arr[j]<k){
        i=j;
        j=2*j;
    }
    //Now calling Simple Binary Search on range i to j.
    return binary_search(arr,i,j,k);
}

/*

Q2:How would you search for an element in an array/list whose size is unknown?

ANS: We can search an element in an array whose size is unknown in O(logn) time complexity provided that the array is in sorted order (here i am taking case of ascending order).We can do this by making some modification in binary search technique.

  ->Take inital value of i as 0 and j as 1.
  ->Now increase j to j*2 until arr[j] exceed the key to be searched.
  ->Now search the key using binary search between i and j.

*/