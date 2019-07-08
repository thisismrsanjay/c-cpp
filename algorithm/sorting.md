##insertion sort
```cpp
#include<stdio.h>

void insertionSort(int arr[],int length){
  int key,i;
  

  for(int j=1;j<length;j++){

    //keeping  value in hand for comaprison
    key = arr[j];
    i=j-1;
    //shifting technique
    while(i>=0 && key<arr[i]){
      arr[i+1]=arr[i];
      i=i-1;
    }
    arr[i+1]=key;
  }
  
}


void printArray(int arr[],int length){
  for(int i=0;i<length;i++){
    printf("%d ",arr[i]);
  }
  printf("\n");
}

int main(){
  int arr[]= {9,6,5,2,1,3,4,7,8};
  int size_of_array = sizeof(arr)/sizeof(arr[0]);

  printf("before insertion sort:- ");
  printArray(arr,size_of_array);

  insertionSort(arr,size_of_array);

  printf("after insertion sort :- ");
  printArray(arr,size_of_array);
  return 0;
}
```